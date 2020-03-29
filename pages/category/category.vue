<template>
	<view >
		<view style="border-top:1px solid #ddd;">
			
			<view style="overflow: auto;position:fixed;top:45px;left:0;bottom:0;width:110px;background:#eee;">
				<view v-for="v,k in data">
					<view @tap="show_m(0, v)" style="padding:12px 10px;text-align:center;font-weight:bold;font-size:18px;text-align:left;">{{v.name}}</view>
					<view v-if="v.sub.length>0">
						
						<view @tap="show_m(1, sv)" style="padding:12px 10px;text-align:center;font-size:18px;;text-align:left;padding-left:20px;" v-for="sv in v.sub">{{sv.name}}</view>
						
					</view>
					
				</view>
				
				
				
			</view>
			
			<view style="margin-left:110px;" v-if="n">
				<view style="text-align:center;line-height:50px;"> - {{n.name}} - </view>
				<view style="text-align:center;color:#fff;border:1px solid #ccc;border-radius:10px;height:120px;margin:0 10px;line-height:120px;background:gray;">
				<image :src="'http://192.168.1.251:8018/storage/'+n.icon" style="height:120px;width:268px;"></image>
					
				</view>
				
				<view style="margin-top:10px;display:flex;flex-wrap: wrap;flex-direction: row;justify-content: space-around;">
					
					<navigator v-for="vv in view" :url="'../product-list/product-list?id='+vv.id+'&title='+vv.name" hover-class="navigator-hover">
					<view style="margin-top:10px;width:70px;text-align:center;padding:3px;">
						<view style="background:gray;border-radius:5px;color:#fff;height:60px;with:60px;line-height:60px;"><image style="height:60px;width:60px;" :src="'http://192.168.1.251:8018/storage/'+vv.icon"></image></view>
						<view>{{vv.name}}</view>
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
				view:[],
				n:null,
			}
		},
		onLoad(){
			this.getData(0,0)
		},
		methods: {
			show_m(level, v){
				if(level == 0 && v.sub.length>0) {
					return;
				}
				this.n = v;
				this.getData(v.id, 1)
				
			},
			getData(id,s){
				var that = this
				uni.request({
					url:'http://192.168.1.251:8018/api/app/product/category?id='+id,
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
						if(s ==0) {
							that.data = res.data.data
						} else {
							that.view = res.data.data
						}
						console.log(that.view)
					},
				})
			}
		}
	}
</script>

<style>

</style>
