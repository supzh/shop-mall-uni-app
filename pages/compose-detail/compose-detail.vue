<template>
	<view style="padding-bottom:75px;">
		
		<view style="position:fixed;bottom:0;background:#fff;left:0;right:0;height:55px;line-height:55px;padding:0 10px;border-top:1px solid #ddd;">
			
			<view style="float:left;"> <checkbox value="cb" checked="true" /> 全选</view>
		
			<view style="float:right;background:#2C405A;color:#fff;padding:0 10px;">去结算</view>
			
			<view style="float:right;margin-right:10px;line-height:20px;font-size:16px;margin-top:10px;">搭配价：<text style="color:orange;">￥0.00</text><br /> <text style="color:#999;font-size:14px;">会员价：￥0.00</text> </view>
			
			<view style="clear:both;"></view>
		</view>
		
		<view class="uni-margin-wrap">
			<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
				<swiper-item>
					<view class="swiper-item uni-bg-red" style="background:#fff;font-size:250px;color:#ccc;">A</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item uni-bg-green" style="background:#fff;font-size:250px;color:#ccc;">B</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item uni-bg-blue" style="background:#fff;font-size:250px;color:#ccc;">C</view>
				</swiper-item>
			</swiper>
		</view>
		
		<view style="background:#fff;margin:10px;box-shadow:1px 1px 2px #ccc;">
					<view style="padding:15px 10px;font-size:17px;">整套LOOK潮流有范，是追求时尚活泼的男士最爱之一</view>
					<view style="display:flex;flex-direction: row;">
						<view style="padding:10px;">
						<view style="background:#f2d39c;width:80px;height:32px;line-height:32px;font-size:16px;text-align:center;border-radius:5px;">推荐理由</view></view>
						<view style="color:#999;font-size:14px;padding-top:5px;">本季色彩类型为秋季型，适合肤色微黄色或偏白色，适合时尚的人群。</view>
					</view>
					
					<view style="display:flex;flex-direction: row;">
						<view style="padding:10px;">
						<view style="background:#f2d39c;width:80px;height:32px;line-height:32px;font-size:16px;text-align:center;border-radius:5px;">搭配规则</view></view>
						<view style="color:#999;font-size:14px;padding-top:5px;">色彩搭配上最好以相近色或同系色来柔和视觉效果，整体更具奢牌搭配的高级感。</view>
					</view>
					
					<view style="display:flex;flex-direction: row;">
						<view style="padding:10px;">
						<view style="background:#f2d39c;width:80px;height:32px;line-height:32px;font-size:16px;text-align:center;border-radius:5px;">推荐理由</view></view>
						<view style="color:#999;font-size:14px;padding-top:5px;">红色提花方领长袖衬衫+豆沙红都市时尚休闲裤</view>
					</view>
		</view>
		
		<view style="background:#333;margin:10px;border-radius:5px;font-size:15px;line-height:50px;padding-left:15px;color:#fff;">
			2件9.5折，3件9折，4件及以上8.8折
			</view>
			
			
			
			<view style="display:flex;flex-direction:row;background:#fff;margin:10px;box-shadow:1px 1px 2px #ccc;">
				
				<view style="line-height:120px;padding:10px;"> <checkbox value="cb" checked="true" /> </view>
				
				<view>
					
					<view style="width:110px;height:110px;border:1px solid #ddd;margin-top:15px;color:#ccc;text-align:center;line-height:110px;">image</view>
					
				</view>
				
				<view style="margin-left:10px;display:flex;flex-direction: column;">
					<view style="font-size:16px;margin-top:10px;">意大利进口面料埃及棉鱼骨纹衬衣</view>
					<view style="font-size:14px;color:#999;">100纯羊毛</view>
					<view style="color:#f2d39c;align-self:flex-end;background:#fff;width:100%;">￥7350.00</view>
				</view>
				
			</view>
			
			<view style="display:flex;flex-direction:row;background:#fff;margin:10px;box-shadow:1px 1px 2px #ccc;">
				
				<view style="line-height:120px;padding:10px;"> <checkbox value="cb" checked="true" /> </view>
				
				<view>
					
					<view style="width:110px;height:110px;border:1px solid #ddd;margin-top:15px;color:#ccc;text-align:center;line-height:110px;">image</view>
					
				</view>
				
				<view style="margin-left:10px;display:flex;flex-direction: column;">
					<view style="font-size:16px;margin-top:10px;">意大利进口面料埃及棉鱼骨纹衬衣</view>
					<view style="font-size:14px;color:#999;">100纯羊毛</view>
					<view style="color:#f2d39c;align-self:flex-end;background:#fff;width:100%;">￥7350.00</view>
				</view>
				
			</view>
			
			<view style="display:flex;flex-direction:row;background:#fff;margin:10px;box-shadow:1px 1px 2px #ccc;">
				
				<view style="line-height:120px;padding:10px;"> <checkbox value="cb" checked="true" /> </view>
				
				<view>
					
					<view style="width:110px;height:110px;border:1px solid #ddd;margin-top:15px;color:#ccc;text-align:center;line-height:110px;">image</view>
					
				</view>
				
				<view style="margin-left:10px;display:flex;flex-direction: column;">
					<view style="font-size:16px;margin-top:10px;">意大利进口面料埃及棉鱼骨纹衬衣</view>
					<view style="font-size:14px;color:#999;">100纯羊毛</view>
					<view style="color:#f2d39c;align-self:flex-end;background:#fff;width:100%;">￥7350.00</view>
				</view>
				
			</view>
					
					
			
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad(){
			uni.setNavigationBarTitle({title: '搭配详情'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			
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
