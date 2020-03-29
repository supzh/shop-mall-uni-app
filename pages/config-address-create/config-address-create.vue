<template>
	<view style="border-top:1px solid #ddd;">
		
		<view>
			<input v-model="name" style="background:#fff;padding:10px;" placeholder="姓名" />
		</view>
		
		<view style="border-top:1px solid #ddd;">
			<input v-model="mobile" style="background:#fff;padding:10px;" placeholder="手机号" />
		</view>
		
		<view style="background:#fff;border-top:1px solid #ddd;">
			<input v-model="province" style="width:80px;background:#fff;padding:10px;float:left;" placeholder="省" />
			<input v-model="city" style="width:80px;background:#fff;padding:10px;float:left;" placeholder="市" />
			<input v-model="area" style="width:80px;background:#fff;padding:10px;float:left;" placeholder="区" />
			<view style="clear:both;"></view>
		</view>
		
		<view style="border-top:1px solid #ddd;">
			<textarea v-model="address" style="background:#fff;padding:10px;width:100%;" placeholder="详细地址"><textarea></textarea>
		</view>
		<view>
			<button @tap="submit">确定</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				name:'',
				mobile:'',
				province:'',
				city:'',
				area:'',
				address:'',
				op:[],
			}
		},
		onLoad(op){
			this.op = op
			console.log(op)
			if(op.t=='edit') {
				this.name = op.name
				this.mobile = op.mobile
				this.province = op.province
				this.city = op.city
				this.area = op.area
				this.address = op.address
			}
			uni.setNavigationBarTitle({title: '新建地址'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			submit(){
				var that =this
				var dat = {
						user_id:1,
						name:that.name,
						mobile:that.mobile,
						province:that.province,
						city:that.city,
						area:that.area,
						address:that.address,
					}
				if(this.op.t=='add') {
					var url = 'http://192.168.1.251:8018/api/app/user/address/create'
				} else {
					var url = 'http://192.168.1.251:8018/api/app/user/address/modify'
					dat.id = this.op.id
				}
				uni.request({
					url:url,
					data:dat,
					header:{},
					success:function(res){
						if(res.data.errcode!=0){
							uni.showToast({
								title: "操作出错",
								"icon":"none",
								duration: 3000
							})
							return
						}
						uni.showToast({
							title: "操作成功",
							"icon":"none",
							duration: 800,
							
						})
						setTimeout(function(){
							uni.navigateBack({
								
							})
						},800)
						
					},
				})
			}
		}
	}
</script>

<style>
page {background:#eee;}
</style>
