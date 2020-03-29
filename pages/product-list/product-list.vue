<template>
	<view >
		<view style="border-top:1px solid #ddd;">
			
		
			<view style="background:#fff;display:flex;justify-content: space-around;text-align: center;border-bottom:1px solid #ddd;">
				<view style="border-right:1px solid #ddd;padding:10px;text-align:center;padding-right:50px;padding-left:30px;">
					销量
				</view>
				<view style="border-right:1px solid #ddd;padding:10px;;padding-right:40px;">
					价格
				</view>
				<view style="padding:10px;;padding-right:30px;">
					新品
				</view>
			</view>
			
			<view style="padding-bottom:20px;">
				<view style="margin-top:10px;display:flex;flex-wrap: wrap;flex-direction: row;justify-content: space-around;">
					
					<navigator v-for="v in data" :url="'../product-detail/product-detail?id='+v.id" hover-class="navigator-hover">
					<view style="margin-top:10px;border:1px solid #ddd;width:170px;text-align:center;padding:0px;">
						<view style="background:gray;color:#fff;height:220px;line-height:220px;"><image style="width:170px;height:220px;" :src="'http://192.168.1.251:8018/storage/'+v.icon"</view>
						<view style="text-align:left;padding:10px;background:#fff;">
							<view style="font-size:15px;">{{v.name}}}</view>
							<view style="font-size:12px;color:#aaa;">{{v.intro}}</view>
							<view style="padding:5px 0;">￥{{v.price}}</view>
						</view>
					</view>
					</navigator>
					
				</view>
				
			</view>
			
			
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
		onLoad(op) {
			uni.setNavigationBarTitle({title: op.title});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
			this.getData(op.id)
		},
		methods: {
			getData(id){
				var that = this
				uni.request({
					url:'http://192.168.1.251:8018/api/app/product/list?category_id='+id,
					data:{},
					header:{},
					success:function(res){
						if(res.data.errcode!=0){
							uni.showToast({
								title: "加载失败",
								"icon":"none",
								duration: 3000
							})
							return
						}
						that.data = res.data.data
						console.log(that.data)
					},
				})
			}
		}
	}
</script>

<style>
page {background:#eee;}
</style>
