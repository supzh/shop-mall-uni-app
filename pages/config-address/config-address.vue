<template>
	<view>
		<view style="margin:10px 0;background:#fff;" v-for="i in data">
			<view style="display:flex;">
				<view style="padding-bottom:10px;">
					<view style="padding:10px;font-size:16px;">{{i.name}}</view>
					<view style="padding-left:10px;font-size:14px;">{{i.province}}{{i.city}}{{i.area}}{{i.address}}</view>
				</view>
				<view style="padding-top:10px;font-size:16px;">{{i.mobile}}</view>
			</view>
			<view style="border-top:1px dotted #ddd;padding:10px;display:flex;justify-content: flex-end;">
				<view><button style="font-size:16px;" @tap="del(i.id)">删除</button> </view>
				<navigator :url="'../config-address-create/config-address-create?t=edit&id='+i.id+'&name='+i.name+'&mobile='+i.mobile+'&province='+i.province+'&city='+i.city+'&area='+i.area+'&address='+i.address" hover-class="navigator-hover">
					<view style="margin-left:10px;"><button style="font-size:16px;">编辑</button></view>
				</navigator>
			</view>	
		</view>
		
		<view>
			
			<navigator url="../config-address-create/config-address-create?t=add" hover-class="navigator-hover"><button>新建地址</button></navigator>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				data:[],
			}
		},
		onShow(){
			this.list()
		},
		onLoad(){
			uni.setNavigationBarTitle({title: '地址管理'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
			this.list()
		},
		methods: {
			list(){
				var that =this
				uni.request({
					url:'http://192.168.1.251:8018/api/app/user/address/list',
					data:{user_id:1},
					header:{},
					success:function(res){
						if(res.data.errcode!=0){
							uni.showToast({
								title: "查询出错",
								"icon":"none",
								duration: 3000
							})
							return
						}
						that.data = res.data.data
					
						console.log(res.data)
					},
				})
			},
			del(id) {
				var that =this
				uni.request({
					url:'http://192.168.1.251:8018/api/app/user/address/delete',
					data:{user_id:1,id:id},
					header:{},
					success:function(res){
						if(res.data.errcode!=0){
							uni.showToast({
								title: "查询出错",
								"icon":"none",
								duration: 3000
							})
							return
						}
						uni.showToast({
							title: "删除成功",
							duration: 3000
						})
						that.list()
					
						console.log(res.data)
					},
				})
			}
		}
	}
</script>

<style>
page {
	background:#eee;
}
</style>
