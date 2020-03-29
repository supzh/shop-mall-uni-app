<template>
	<view v-if="product" style="border-top:1px solid #ddd;padding-bottom:65px;">
		
		<view  style="dislay:flex;flex-direction:row;background:#fff;right:0;text-align:center;position:fixed;left:0;bottom:0;height:55px;border-top:1px solid #ddd;">
			
			<navigator url="../cart/cart" hover-class="navigator-hover">
			<view style="float:left;padding-left:10px;padding-right:10px;width:40px;border-right:1px solid #ddd;background:#fff;display:flex;flex-direction: column;justify-content:center;">
				<view style ="font-size:12px;width:40px;height:36px;background:#fff;line-height:36px;font-weight:bold;">icon</view>
				<view style="font-size:14px;background:#fff;">购物袋</view>
			</view>
			</navigator>
			
			<view style="float:left;padding-left:10px;padding-right:10px;width:40px;border-right:1px solid #ddd;background:#fff;display:flex;flex-direction: column;justify-content:center;">
				<view style ="font-size:12px;width:40px;height:36px;background:#fff;line-height:36px;font-weight:bold;">icon</view>
				<view style="font-size:14px;background:#fff;">咨询</view>
			</view>
			
			<view @tap="addToCart" style="float:left;padding-left:10px;padding-right:10px;width:auto;height:55px;font-size:14px;background:orange;display:flex;flex-direction: column;justify-content:center;">
				加入购物袋
			</view>
			
			<view style="float:right;padding-left:10px;padding-right:20px;width:auto;height:55px;font-size:13px;background:#2C405A;display:flex;flex-direction: column;justify-content:center;color:#fff;">
				预约量体<br />
				<text style="font-size:11px;">新人礼包可用</text>
			</view>
			
		</view>
		
		<view v-show="showm" style="z-index:99999;border-top:1px solid #ddd;background:#fff;position:fixed;top:44px;overflow:auto;;left:0;right:0;bottom:0;padding-top:30px;">
			
			<view @tap="switch_show" style="position:fixed;top:44px;left:0;right:0;background:#fff;text-align:center;font-size:18px;line-height:32px;border-bottom:1px slid #ddd;background:#eee;font-weight:bold;font-size:16px;">关闭</view>
			
			<view  @tap="csel_m(v.info)" v-for="v in product.material" style="display:flex;flex-direction:row;background:#fff;padding-bottom:10px;border-bottom:1px solid #ddd;">			
				<view style="margin-left:10px;">
					<view style="width:140px;height:80px;border:1px solid #ddd;margin-top:10px;color:#ccc;text-align:center;line-height:80px;"><image style="width:140px;height:80px;" :src="'http://192.168.1.251:8018/storage/'+v.info.photo"></image></view>
				</view>
				<view style="margin-left:10px;display:flex;flex-direction: column;padding-bottom:10px;padding-right:10px;">
					<view style="font-size:14px;margin-top:10px;line-height:24px;">编号：{{v.info.no}}<br />颜色：{{v.info.color}}<br />成分：{{v.info.text}}</view>
				</view>
			</view>
		</view>
		
		
		
		
		<view v-if="product" style="display:flex;flex-direction:row;background:#fff;padding-bottom:10px;">			
			<view style="margin-left:10px;">
				<view style="width:70px;height:110px;border:1px solid #ddd;margin-top:10px;color:#ccc;text-align:center;line-height:110px;">
					<image :src="'http://192.168.1.251:8018/storage/'+product.icon"></image>
				</view>
				
			</view>
			
			<view style="margin-left:10px;display:flex;flex-direction: column;padding-bottom:10px;padding-right:10px;">
				<view style="font-size:14px;margin-top:10px;">{{product.name}}</view>
				<view style="color:#a57a40;background:#fff;width:100%;margin-top:5px;line-height:20px;font-size:16px;"><text style="font-size:14px;color:#222;">售价：</text>￥{{product.price}}<br /><text style="color:#ccc;font-size:14px;text-decoration: line-through;">吊牌价￥{{product.tag_price}}</text></view>
			</view>
			
		</view>
		
		<view style="text-align:center;font-size:12px;color:#999;padding:10px;"> --------------------- 可调细节 可选工艺 --------------------- </view>
		


			<view v-if="sel_m" @tap="switch_show" style="margin-top:0px;padding-top:10px;background:#fff;min-height:140px;">
				<view style="margin-left:10px;padding-left:5px;font-size:16px;border-left:4px solid #302b44">面料</view>
				<view style="display:flex">
					<view style="width:100%;margin-top:10px;">
						<view style="background:#ddd;margin:0 10px;;height:70px;">	
							<view style="position:absolute;right:10px;background:#eee;height:70px;font-size:14px;padding:0px;"><view style="padding:5px;">编号：{{sel_m.no}}<br />颜色：{{sel_m.color}}<br />成分：{{sel_m.text}}</view></view>
						</view>
					</view>
				</view>
				<view style="margin-top:10px;float:right;color:#999;font-size:14px;">修改面料>></view>
			</view>

		
		<view  v-for="v,k in product.arts" style="margin-top:0px;padding-top:10px;background:#fff;border-top:1px solid #ddd;">
			<view style="margin-left:10px;padding-left:5px;font-size:16px;border-left:4px solid #302b44">{{v.info.name}}</view>
			<view style="display:flex;flex-wrap: wrap;justify-content: space-around;">
				<view @tap="csel_a(sv.info, k, sk)" v-for="sv,sk in v.item" style="padding:5px;text-align:center;">
					<view :class="(sv.info.sel)?'f':''" style="width:80px;height:80px;line-height:80px;border:2px solid #ddd;font-size:14px;color:#999;"><image style="width:80px;height:80px;" :src="'http://192.168.1.251:8018/storage/'+sv.info.photo"></image></view>
					<view style="font-size:14px;line-height:32px;">{{sv.info.name}}</view>
				</view>		
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				product:{},
				showm:false,
				sel_m :null,
				sel_a:[],
			}
		},
		onLoad(op) {
			uni.setNavigationBarTitle({title: '调整工艺'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
			this.getPInfo(op.product_id)
		},
		methods: {
			addToCart(){
				var that = this
				var id = that.data.id
				var custom_info = {}
				uni.request({
					url:'http://192.168.1.251:8018/api/app/order/cart/add',
					data:{
						user_id:1,
						product_id:id,
						num:1,
						custom_info:custom_info
					},
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
				
				uni.navigateTo({
					url:'../cart/cart',
				})
			},
			csel_a(v, k, sk) {
				for(var i in this.product.arts[k].item) {
					this.product.arts[k].item[i].info.sel = false
				}
				this.product.arts[k].item[sk].info.sel = true
			},
			csel_m(v) {
				this.sel_m = v
				this.switch_show()
			},
			switch_show(){
				if(this.showm) {
					this.showm=false
					uni.setNavigationBarTitle({title: '调整工艺'});
				}else {
					this.showm=true
					uni.setNavigationBarTitle({title: '选择面料'});
				}
				
			},
			getPInfo(id){
				var that = this
				uni.request({
					url:'http://192.168.1.251:8018/api/app/product/detail?id='+id,
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
						that.product = res.data.data
						that.sel_m = that.product.default_material
						console.log(that.product)
					},
				})
			}
		}
	}
</script>

<style>
	.f {border:2px solid #222222!important;}
page {background:#eee;}
</style>
