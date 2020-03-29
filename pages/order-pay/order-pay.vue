<template>
	<view style="border-top:1px solid #ddd;">
		
		<view style="background:#fff;color:orange;text-align:center;padding:20px;">￥589.00</view>
		
		<view style="background:#fff;padding-top:10px;text-align:left;margin-top:10px;">
			<view style="border-bottom:1px solid #ddd;">
				<view style="margin-left:10px;padding-bottom:10px;font-size:16px;">钱包支付<text style="padding-left:35px;color:#aaa;font-size:14px;">可用余额￥0.00</text>
				<view style="float:right;"><radio /></view>
				</view>
				
			</view>
			<view style="border-bottom:1px solid #ddd;">
				<view style="margin-left:10px;padding-bottom:10px;padding-top:10px;font-size:16px;">微信支付<text style="padding-left:35px;color:#aaa;font-size:14px;">绿色通道，安全便捷</text>
				<view style="float:right;"><radio /></view>
				</view>
				
			</view>
			
			<view style="border-bottom:1px solid #ddd;">
				<view style="margin-left:10px;padding-top:10px;padding-bottom:10px;font-size:16px;">支付宝支付<text style="padding-left:35px;color:#aaa;font-size:14px;">绿色通道，安全便捷</text>
				<view style="float:right;"><radio /></view>
				</view>
				
			</view>
		
		</view>
		
		
		<view @tap="submit()" style="background:#2C405A;color:#fff;font-size:16px;position:fixed;bottom:0;left:0;right:0;text-align:center;padding:12px;">确认付款</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad() {
			uni.setNavigationBarTitle({title: '订单支付'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			
		}
	}
</script>

<style>
page {background:#eee;}
</style>
