<template>
	<view>

		<view class="uni-margin-wrap"style="border-bottom:10px solid #fff;">
			<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
		
				<swiper-item v-for="i in banner">
					<view class="swiper-item uni-bg-red" style="background:#fff;"><image :src="'http://192.168.1.251:8018/storage/'+i.photo"></image></view>
				</swiper-item>
			
			</swiper>
		</view>
		
		<navigator url="../seckill/seckill" hover-class="navigator-hover">
		<view style="background:#333;color:#fff;border-radius:10px;margin:10px;float:left;clear:both;">
			<view style="float:left;width:60%;">
				<view style="float:left;">
					<view style="font-size:24px;padding:20px 0 0 20px;float:left;">
						限时秒杀
					</view>
					<view style="background:#F0AD4E;color:#333;margin-top:23px;margin-left:6px;border-radius:30px;float:left;clear:right;width:80px;text-align:center;">15点场</view>
				</view>
				
				<view style="float:left;font-size:18px;padding:6px 10px;border-left:3px solid #fff;margin:20px 0 20px 20px;">
					限量精品 低至5.5折
				</view>
			</view>
			
			<view style="float:right;font-size:16px;padding-top:50px;padding-right:20px;">
				<view style="float:left;">
					距结束
				</view>
				<view style="float:left;">
					00:00:00
				</view>
			</view>
		</view>
		<view style="clear:both;"></view>
		<view style="display:flex;flex-direction:row;flex-wrap:nowrap;justify-content:space-around;padding:10px;">
			<view style="width:100px;background:#fff;padding:3px;border-radius:10px;box-shadow:1px 1px 2px #aaa">
				<view style="height:120px;line-height:120x;color:gray;text-align:center;">image</view>
				<view>
				     <view>￥1000</view>
					<view style="color:#999;text-decoration:line-through; ">￥2000</view>
				</view>
			</view>
				
			<view style="width:100px;background:#fff;padding:3px;border-radius:10px;box-shadow:1px 1px 2px #aaa">
				<view style="height:120px;line-height:120x;color:gray;text-align:center;">image</view>
				<view>
					 <view>￥2000</view>
					<view style="color:#999;text-decoration:line-through; ">￥2000</view>
				</view>
			</view><view style="width:100px;background:#fff;padding:3px;border-radius:10px;box-shadow:1px 1px 2px #aaa">
					<view style="height:120px;line-height:120x;color:gray;text-align:center;">image</view>
					<view>
						 <view>￥3000</view>
						<view style="color:#999;text-decoration:line-through; ">￥2000</view>
					</view>
				</view>
				
		</view>
		
		<view style="display:flex;justify-content: center;">
		<view style="background:#F0AD4E;color:#333;margin-top:3px;margin-left:6px;border-radius:30px;float:left;clear:right;width:80px;text-align:center;">15点场</view>
		</view>
		</navigator>
		
	
		<view style="margin-top:20px;clear:both;height:200px;text-align:center;line-height:200px;background:#fff;">
			
			橱窗展示
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
				
				
			}
		},
		onLoad(){
			this.getContents()
		},
		methods: {
			getContents(){
				var that = this
				uni.request({
					url:'http://192.168.1.251:8018/api/app/home/display',
					data:{},
					header:{},
					success:function(res){
						if(res.data.errcode!=0){
							uni.showToast({
								title: "加载内容失败",
								"icon":"none",
								duration: 3000
							})
							return
						}
						that.banner = res.data.data.topBanner
					},
				})
			}
		}
	}
</script>

<style>
	page {background:#f5f5f5;}
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
