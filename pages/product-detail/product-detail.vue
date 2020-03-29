<template>
	
	
	
	<view style="border-top:1px solid #ddd;" v-if="data">
			
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
			
			<view class="uni-margin-wrap">
				<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
					<swiper-item>
						<view class="swiper-item uni-bg-red" style="background:#fff;">A</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item uni-bg-green" style="background:#fff;">B</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item uni-bg-blue" style="background:#fff;">C</view>
					</swiper-item>
				</swiper>
			</view>
			<view style="padding:5px;background:#fff;border-top:1px solid #ddd;">
				<view style="float:left;font-size:15px;background:#fff;">
					<view style="font-weight:bold;line-height:32px;padding-top:10px;">{{data.name}}</view>
					<view>
						<view style="background:black;color:#fff;width:35px;float:left;font-size:12px;text-align:center;border-radius:2px;">精品</view>
						<view style="font-size:12px;color:#aaa;float:left;">{{data.intro}}</view>
						<view style="clear:both;"></view>
					</view>
				</view>
				<view style="float:right;width:120px;background:#fff;font-size:13px;text-align:right;">
					<view style="text-align:center;background:#fff;border:1px solid #ccc;border-radius:5px;line-height:35px;margin-top:10px;height:35px;width:80px;float:right;clear:both;color:blue;">image</view>
					<view style="float:right;clear:both;margin-top:5px;">查看面料介绍></view>
				</view>
				<view style="clear:both;"></view>
				
				
				<view style="background:#fff;">
					<view style="margin:10px;padding:0px 0px;background:#333;color:#fff;border-radius:10px;font-size:15px;display:flex;justify-content: space-between;">
						<view style="padding:10px 8px;font-size:13px;font-weight:bold;">升级VIP，购买该商品预计节省735元</view>
						<view style="padding:10px 8px;font-size:13px;background:orange;border-radius:10px;color:#333;font-weight:bold;">立即开通>></view>
					</view>
				</view>
				
				<view style="display:flex;justify-content: space-around;font-size:13px;color:#aaa;line-height:30px;">
					<view>√ 免费上门量体</view>
					<view>√ 一人一版定制</view>
					<view>√ 365天无忧售后</view>
					<view style="color:#333;font-size:18px;"> >	</view>
				</view>

			</view>
			
			<navigator :url="'../product-art/product-art?product_id='+data.id" hover-class="navigator-hover">
				<view style="background:#fff;margin-top:15px;margin-bottom:15px;">			
					<view style="justify-content: left;padding:10px;font-size:16px;line-height:30px;">
							<view style="float:left;">可用面料/工艺</view>
							<view style="color:#333;font-size:18px;float:right;"> >	</view>
							<view style="clear:both;"></view>
					</view>
				</view>
			</navigator>
			
			<view style="background:#fff;margin-top:15px;margin-bottom:15px;">
			
				<view style="justify-content: left;padding:10px;font-size:16px;line-height:30px;border-bottom:1px solid #ddd;">
						<view style="float:left;">用户评价</view>
						<view style="color:#333;font-size:18px;float:right;"> <text style="color:orange;font-size:14px;">5分</text> >	</view>
						<view style="clear:both;"></view>
				</view>
				<view style="padding:10px;">
					
					<view>
						<view style="float:left;width:35px;height:35px;border-radius:100%;background:#2C405A;"></view>
						<view style="float:left;padding-left:10px;">
							<view style="font-size:14px;">张**</view>
							<view style="color:#aaa;font-size:12px;">2020-03-24</view>
						</view>
						<view style="clear:both;"></view>
					</view>
					<view style="padding-top:10px;font-size:12px;color:#333;">
						<view style="float:left;padding:4px 6px;background:#eee;border-radius:3px;">面料：40077/13</view>
						<view style="margin-left:10px;float:left;padding:4px 6px;background:#eee;border-radius:3px;">颜色：蓝色</view>
						<view style="clear:both;"></view>
					</view>
					
					<view style="padding-top:10px;font-size:12px;color:#333;">
						<view style="float:left;padding:4px 6px;color:#999;background:#fff;border:1px solid #ddd;border-radius:20px;">尺寸合身</view>
						<view style="margin-left:10px;float:left;padding:4px 6px;color:#999;background:#fff;border:1px solid #ddd;border-radius:20px;">面料质量好</view>
						<view style="margin-left:10px;float:left;padding:4px 6px;color:#999;background:#fff;border:1px solid #ddd;border-radius:20px;">款式好看</view>
						<view style="margin-left:10px;float:left;padding:4px 6px;color:#999;background:#fff;border:1px solid #ddd;border-radius:20px;">包装精美</view>
						
						<view style="clear:both;"></view>
					</view>
					
					<view style="padding-top:10px;font-size:16px;color:#333;">
						我只想说，完美，就是有点小贵<br />很喜欢
					</view>
					
				</view>
			
			</view>
			
			<view style="background:#fff;margin-top:15px;margin-bottom:70px;text-align:center;padding:20px;min-height:200px;">
			商品详情
			<view :v-html="data.description_content"></view>
			</view>
			

	</view>
</template>

<script>
	export default {
		data() {
			return {
				banner: [1],
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				data:null
			}
		},
		onLoad(op) {
			uni.setNavigationBarTitle({title: '商品详情'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
			this.getData(op.id)
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
			getData(id){
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
	.uni-margin-wrap {
		width:100%;
		margin:0 0rpx;
	}
	.swiper {
		height: 800rpx;
	}
	.swiper-item {
		display: block;
		height: 800rpx;
		line-height: 800rpx;
		text-align: center;
	}

	.swiper-list {
		margin-top: 40rpx;
		margin-bottom: 0;
	}

	.uni-common-mt{
		margin-top:60rpx;
		position:relative;
	}

	.info {
		position: absolute;
		right:20rpx;
	}

    .uni-padding-wrap {
        width:550rpx;
        padding:0 100rpx;
    }
</style>
