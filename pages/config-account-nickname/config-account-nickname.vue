<template>
	<view>
		
		<view style="font-size:13px;color:#777;padding:10px;">为方便客服人员联系，建议填写真实姓名</view>
		<view> <input v-model="nickname"  style="background:#fff;padding:10px;color:#333;" class="uni-input" focus placeholder="" /></view>
		<view>
			<view style="background:#2C405A;color:#fff;text-align:center;margin:10px;padding:10px 0;font-size:16px;" @tap="submit">确定</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				account:{},
				nickname:'',
			}
		},
		onLoad(){
			uni.setNavigationBarTitle({title: '修改用户姓名'});
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
					that.nickname = that.account.nickname
					console.log(res.data)
				},
			})
		},
		methods: {
			submit(){
				uni.request({
					url:'http://192.168.1.251:8018/api/app/user/nickname',
					data:{user_id:1, nickname:this.nickname},
					header:{},
					success:function(res){
						if(res.data.errcode!=0){
							uni.showToast({
								title: "修改失败",
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
