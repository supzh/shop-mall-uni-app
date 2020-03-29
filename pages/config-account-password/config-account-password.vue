<template>
	<view>
		
		<view style="font-size:13px;color:#777;padding:10px;">发送验证码到手机{{account.account}}进行验证</view>
		<view> <input v-model="code"  style="background:#fff;padding:10px;color:#333;" class="uni-input" focus placeholder="请输入验证码" />
		<view v-if="is_send_code==false" @tap="sendcode" style="position:absolute;right:20px;margin-top:-30px;font-size:14px;color:#FF3333;">获取验证码</view>
		<view @tap="sendcode" v-else style="position:absolute;right:20px;margin-top:-30px;font-size:14px;color:#999;">{{count}}秒后可重新发送</view>
		</view>
		
		<view> <input v-model="newpass"  style="background:#fff;padding:10px;color:#333;" class="uni-input" focus placeholder="密码长度 6-12 个字符" /></view>
		
		
		<view>
			<view style="background:#2C405A;color:#fff;text-align:center;margin:10px;padding:10px 0;font-size:16px;" @tap="submit">修改密码</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				is_send_code:false,
				account:{},
				code:'',
				newpass:'',
				count:60,
			}
		},
		onLoad(){
			uni.setNavigationBarTitle({title: '修改密码'});
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
			
					console.log(res.data)
				},
			})
		},
		methods: {
			sendcode(){
				if(this.is_send_code) {
					uni.showToast({
						icon:"none",
						duration:3000,
						title:"请您于"+this.count+"秒后重试。"
					})
					return
				}
				this.is_send_code = true
				
				uni.request({
					url:'http://192.168.1.251:8018/api/app/user/nickname',
					data:{user_id:1, nickname:this.nickname},
					header:{},
					success:function(res){
						if(res.data.errcode!=0){
							uni.showToast({
								title: "修改失败("+res.data.errmsg+")",
								"icon":"none",
								duration: 3000
							})
							return
						}
						uni.showToast({
							title:"修改成功",
							duration:3000
						})
					},
				})
				
				var that = this
				var t = function(){
					that.count--
					if(that.count<=0) {
						that.is_send_code = false
					}
					setTimeout(t, 1000)
				}
				setTimeout(t,1000)
			},
			submit(){
				uni.request({
					url:'http://192.168.1.251:8018/api/app/user/pass',
					data:{user_id:1, code:this.code, pass:this.newpass},
					header:{},
					success:function(res){
						if(res.data.errcode!=0){
							uni.showToast({
								title: "修改失败("+res.data.errmsg+")",
								"icon":"none",
								duration: 3000
							})
							return
						}
						uni.showToast({
							title:"修改成功",
							duration:3000
						})
					},
				})
			}
		}
	}
</script>

<style>
page {background:#eee;}
</style>
