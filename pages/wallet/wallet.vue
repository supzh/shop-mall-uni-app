<template>
	<view style="border-top:1px solid #ddd;">
		
		<view style="background:#fff;display:flex;justify-content: space-around;">
			
			<view class="c">本周</view>
			
			<view class="c">本月</view>
			
			<view class="c">上月</view>
			
			<view class="c f">更早</view>
			
		</view>
		
		<view>
			<view style="margin:10px;padding:10px;border-bottom:1px solid #ddd;">
				
				<view style="float:left;">充值</view>
				<view style="float:right;text-align:right;">
					<view style="color:orange;">+ 5000.00</view>
					<view style="font-size:12px;color:#999;">05-07 10:10</view>
				</view>
				<view style="clear:both;"></view>
			</view>
			
			<view style="margin:10px;padding:10px;border-bottom:1px solid #ddd;">
				
				<view style="float:left;">充值</view>
				<view style="float:right;text-align:right;">
					<view style="color:orange;">+ 5000.00</view>
					<view style="font-size:12px;color:#999;">05-07 10:10</view>
				</view>
				<view style="clear:both;"></view>
			</view>
			
			<view style="margin:10px;padding:10px;border-bottom:1px solid #ddd;">
				
				<view style="float:left;">充值</view>
				<view style="float:right;text-align:right;">
					<view style="color:orange;">+ 5000.00</view>
					<view style="font-size:12px;color:#999;">05-07 10:10</view>
				</view>
				<view style="clear:both;"></view>
			</view>
			
			<view style="margin:10px;padding:10px;border-bottom:1px solid #ddd;">
				
				<view style="float:left;">充值</view>
				<view style="float:right;text-align:right;">
					<view style="color:orange;">+ 5000.00</view>
					<view style="font-size:12px;color:#999;">05-07 10:10</view>
				</view>
				<view style="clear:both;"></view>
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
		onLoad(op){
			uni.setNavigationBarTitle({title: '钱包明细'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			
		}
	}
</script>

<style>
	.c{ color:#999;font-size:16px;padding:10px;}
	.f{color:#222;border-bottom:3px solid #2C405A;}
page {background:#eee;}
</style>
