<template>
	<view style="border-top:1px solid #ddd;padding-bottom:80px;">
		
		<view>
			<view style="border-left:4px solid #2C405A;margin:10px;padding-left:10px;font-size:16px;">具体建议内容</view>
			<view style="">
				<textarea v-model="text" style="margin:10px;padding:10px;background:#eee;width:auto;border-radius:5px;"></textarea>
				
			</view>
		</view>
		
		<view>
			<view style="border-left:4px solid #2C405A;margin:10px;padding-left:10px;font-size:16px;">上传图片</view>
			<view style="">
				
				<view class="uni-uploader-body">
					<view class="uni-uploader__files">
						<block v-for="(image,index) in imageList" :key="index">
							<view class="uni-uploader__file" style="padding-left:10px;">
								<image class="uni-uploader__img" :src="image" :data-src="image" @tap="previewImage"></image>
							</view>
						</block>
						<view style="clear:both;"></view>
						<view class="uni-uploader__input-box" >
							<view class="uni-uploader__input" @tap="chooseImage" style="margin-left:10px;width:120px;height:120px;border:1px solid #ddd;font-size:80px;line-height:120px;color:#ccc;font-weight:bold;text-align:center;">+</view>
						</view>
					</view>
				</view>
				
				
			</view>
		</view>
		
		
		
		<view @tap="submit()" style="background:#2C405A;color:#fff;font-size:16px;position:fixed;bottom:0;left:0;right:0;text-align:center;padding:12px;">提交</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				text:'',
				photos:[],
				imageList:[],
				sourceTypeIndex:2,
				sourceType: ['拍照', '相册', '拍照或相册'],
				countIndex: 8,
				count: [1, 2, 3, 4, 5, 6, 7, 8, 9],
			}
		},
		onLoad(op){
			uni.setNavigationBarTitle({title: '意见反馈'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			submit(){
				
				var ps = ''
				console.log(this.photos)
				for(var i in this.photos) {
					ps+=','+this.photos[i]
				}
				
				uni.request({
					url:'http://192.168.1.251:8018/api/app/user/feedback',
					data:{user_id:1, description:this.text,photos:ps},
					header:{},
					success:function(res){
					
						if(res.data.errcode!=0){
							uni.showToast({
								title: "反馈失败",
								"icon":"none",
								duration: 3000
							})
							return
						}
						uni.showToast({
							title: "反馈成功！",
							duration: 3000
						})
					},
				})
			},
			
			chooseImage: async function() {
					
					var sourceType = [
						['camera'],
						['album'],
						['camera', 'album']
					]
					var sizeType = [
						['compressed'],
						['original'],
						['compressed', 'original']
					]
					
					// #ifdef APP-PLUS
					// TODO 选择相机或相册时 需要弹出actionsheet，目前无法获得是相机还是相册，在失败回调中处理
					if (this.sourceTypeIndex !== 2) {
						let status = await this.checkPermission();
						if (status !== 1) {
							return;
						}
					}
					// #endif
				
					var that = this
					uni.chooseImage({
						sourceType: sourceType[this.sourceTypeIndex],
						sizeType: sizeType[this.sizeTypeIndex],
						count: this.imageList.length + this.count[this.countIndex] > 9 ? 9 - this.imageList.length : this.count[this.countIndex],
						success: (res) => {
							this.image = res.tempFilePaths
							
							uni.uploadFile({
								url: 'http://192.168.1.251:8018/api/uploadfile', //仅为示例，非真实的接口地址
								filePath: this.image[0],
								name: 'file',
						
								complete: (uploadFileRes) => {
									
									var ures = JSON.parse(uploadFileRes.data)
										
									if(ures.errcode !=0){
										uni.hideLoading()
										uni.showToast({
											icon:"none",
											title:"上传出错",
											duration: 3000
										})
										return;
									}
										uni.hideLoading()
									var serverpath = ures.path
									this.photos.push(serverpath)
									var that = this
									
								}
							});
							
							uni.showLoading({
							
							})
							
							this.imageList = this.imageList.concat(res.tempFilePaths);
							console.log(this.image)
						},
						fail: (err) => {
							// #ifdef APP-PLUS
							if (err['code'] && err.code !== 0 && this.sourceTypeIndex === 2) {
								this.checkPermission(err.code);
							}
							// #endif
							// #ifdef MP
							uni.getSetting({
								success: (res) => {
									let authStatus = false;
									switch (this.sourceTypeIndex) {
										case 0:
											authStatus = res.authSetting['scope.camera'];
											break;
										case 1:
											authStatus = res.authSetting['scope.album'];
											break;
										case 2:
											authStatus = res.authSetting['scope.album'] && res.authSetting['scope.camera'];
											break;
										default:
											break;
									}
									if (!authStatus) {
										uni.showModal({
											title: '授权失败',
											content: 'Hello uni-app需要从您的相机或相册获取图片，请在设置界面打开相关权限',
											success: (res) => {
												if (res.confirm) {
													uni.openSetting()
												}
											}
										})
									}
								}
							})
							// #endif
						}
					})
				},
				isFullImg: function() {
					return new Promise((res) => {
						uni.showModal({
							content: "已经有9张图片了,是否清空现有图片？",
							success: (e) => {
								if (e.confirm) {
									this.imageList = [];
									res(true);
								} else {
									res(false)
								}
							},
							fail: () => {
								res(false)
							}
						})
					})
				},
				previewImage: function(e) {
					var current = e.target.dataset.src
					uni.previewImage({
						current: current,
						urls: this.imageList
					})
				},
				async checkPermission(code) {
					let type = code ? code - 1 : this.sourceTypeIndex;
					let status = permision.isIOS ? await permision.requestIOS(sourceType[type][0]) :
						await permision.requestAndroid(type === 0 ? 'android.permission.CAMERA' :
							'android.permission.READ_EXTERNAL_STORAGE');
				
					if (status === null || status === 1) {
						status = 1;
					} else {
						uni.showModal({
							content: "没有开启权限",
							confirmText: "设置",
							success: function(res) {
								if (res.confirm) {
									permision.gotoAppSetting();
								}
							}
						})
					}
				
					return status;
				}
			}
		
	}
</script>

<style>
page {background:#fff}
</style>
