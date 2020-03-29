<template>
	<view style="border-top:1px solid #ddd;">
		
		<view class="f"  @tap="chooseImage">
				<view class="l">用户头像</view>
				<view class="r">
					<view style="float:right;padding-left:10px;">></view>
					<view style="float:right;width:30px;height:30px;background:#eee;border-radius:100%;margin-top:10px;text-align:center;line-height:30px;"><image style="max-width:30px;max-height:30px;border-radius:100%;" v-if="image.length>0" :src="image[0]"></image><image  style="max-width:30px;max-height:30px;border-radius:100%;"  v-else :src="'http://192.168.1.251:8018/storage/'+account.headimg"></image></view>
					<view style="clear:both;"></view>
				</view>
		</view>
		<navigator url="../config-account-nickname/config-account-nickname" hover-class="navigator-hover">
		<view class="f">
			<view class="l">用户昵称</view>
			
			<view class="r"><view style="float:right;padding-left:10px;">></view>
					<view style="float:right;">{{account.nickname}}</view>
					<view style="clear:both;"></view>
			</view>
		</view></navigator>
			<navigator url="../config-account-password/config-account-password" hover-class="navigator-hover">
		<view class="f">
			<view class="l">账户密码</view>
		
			<view class="r"><view style="float:right;padding-left:10px;">></view>
					<view style="clear:both;"></view></view>
		
		</view>	</navigator>
		
		<view class="f">
			<view class="l">登陆账号</view>
			<view class="r"><view style="float:right;padding-left:10px;">{{account.account}}</view>
					<view style="clear:both;"></view></view>
		</view>
		
		<view class="f">
			<view class="l">您的生日</view>
			<view class="r"><view style="float:right;padding-left:10px;"></view>
					
					<view>
						
						<picker mode="date" :value="account.birthday" :start="startDate" :end="endDate" @change="bindDateChange">
							<view class="uni-input">{{date}}</view>
						</picker>
						
					</view>
					<view style="clear:both;"></view></view>
		</view>
		
		<navigator url="../config-address/config-address" hover-class="navigator-hover">
			<view class="f">
				<view class="l">地址管理</view>
				<view class="r"><view style="float:right;padding-left:10px;">></view>
				<view style="clear:both;"></view></view>
			</view>
		</navigator>
		
		<view class="f" style="text-align:center;font-weight:bold;margin-top:10px;border-top:1px solid #ddd;">
				账户注销
		</view>
		
	</view>
</template>

<script>
	//import permision from "../../common/permission.js"
	function getDate(type) {
		const date = new Date();
	
		let year = date.getFullYear();
		let month = date.getMonth() + 1;
		let day = date.getDate();
	
		if (type === 'start') {
			year = year - 60;
		} else if (type === 'end') {
			year = year + 2;
		}
		month = month > 9 ? month : '0' + month;;
		day = day > 9 ? day : '0' + day;
	
		return `${year}-${month}-${day}`;
	}
	export default {
		data() {
			return {
				imageList:[],
				sourceTypeIndex:2,
				sourceType: ['拍照', '相册', '拍照或相册'],
				countIndex: 8,
				count: [1, 2, 3, 4, 5, 6, 7, 8, 9],
				image:[],
				account:{headimg:''},
				date: getDate({
					format: true
				}),
				startDate:getDate('start'),
				endDate:getDate('end'),
			}
		},
		onLoad(){
			uni.setNavigationBarTitle({title: '账户信息'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
			var that =this
			uni.request({
				url:'http://192.168.1.251:8018/api/app/user/account',
				data:{user_id:1},
				header:{},
				success:function(res){
					if(res.data.errcode!=0){
						uni.showToast({
							title: "查询账户信息出错",
							"icon":"none",
							duration: 3000
						})
						return
					}
					that.account = res.data.data
					that.date = that.account.birthday
					console.log(res.data)
				},
			})
		},
		methods: {
			
			bindDateChange: function(e) {
				this.date = e.detail.value
				var that =this
				uni.request({
					url:'http://192.168.1.251:8018/api/app/user/birth',
					data:{user_id:1,birth:that.date},
					header:{},
					success:function(res){
						if(res.data.errcode!=0){
							uni.showToast({
								title: "查询账户信息出错",
								"icon":"none",
								duration: 3000
							})
							return
						}
						uni.showToast({
							title: "修改生日成功",
							"icon":"none",
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
								var serverpath = ures.path
								var that = this
								uni.request({
									url:'http://192.168.1.251:8018/api/app/user/head',
									data:{user_id:1, img:serverpath},
									header:{},
									success:function(res){
										uni.hideLoading()
										if(res.data.errcode!=0){
											uni.showToast({
												title: "上传失败",
												"icon":"none",
												duration: 3000
											})
											return
										}
										uni.showToast({
											title: "上传成功！",
											duration: 3000
										})
									},
								})
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
	.f {float:left;background:#fff;clear:both;width:100%;height:50px;border-bottom:1px solid #ddd;line-height:50px;}
	.l{float:left;padding-left:15px;font-weight:bold;}
	.r{float:right;font-size:14px;color:#999;padding-right:15px;}
	
page {background:#eee;}
</style>
