<template>
	<view style="border-top:1px solid #ddd;padding-bottom:80px;">
		
		<navigator url="../wallet/wallet" hover-class="navigator-hover">
		<view style="background:#fff;padding:10px;padding-top:15px;text-align:left;">
			<view style="font-size:16px;">我的可用余额 <text style="padding-left:10px;color:orange;">明细</text></view>
			
			<view style="text-align:center;font-size:20px;padding:10px;">￥0.00</view>
		</view>
		</navigator>
		
		<view style="background:#fff;padding:10px;padding-top:15px;text-align:left;margin-top:10px;">
			<view style="font-size:16px;">钱包充值</view>
			
			<view style="display:flex;margin-top:10px;justify-content: space-between;flex-wrap: wrap;flex-direction: row;">
				
				<view style="margin-top:10px;padding:20px;text-align:center;border:1px solid orange;background:#efefef;border-radius:10px;color:orange;font-size:14px;"><text style="font-size:18px;">3000</text>元<br />送50</view>
				
				<view style="margin-top:10px;padding:20px;text-align:center;border:1px solid #ddd;background:#efefef;border-radius:10px;color:#333;font-size:14px;"><text style="font-size:18px;">3000</text>元<br />送50</view>
				
				<view style="padding:20px;margin-top:10px;text-align:center;border:1px solid #ddd;background:#efefef;border-radius:10px;color:#333;font-size:14px;"><text style="font-size:18px;">3000</text>元<br />送50</view>
				
				<view style="padding:20px;text-align:center;margin-top:10px;border:1px solid #ddd;background:#efefef;border-radius:10px;color:#333;font-size:14px;"><text style="font-size:18px;">3000</text>元<br />送50</view>
				
			</view>
		
		</view>
		
		<view style="background:#fff;padding-top:15px;text-align:left;margin-top:10px;">
			<view style="font-size:16px;padding:10px;">支付方式</view>
			
			<view style="border-bottom:1px solid #ddd;">
				<view style="margin-left:10px;padding-bottom:10px;font-size:16px;">微信支付<text style="padding-left:35px;color:#aaa;font-size:14px;">绿色通道，安全便捷</text>
				<view style="float:right;"><radio /></view>
				</view>
				
			</view>
			
			<view style="border-bottom:1px solid #ddd;">
				<view style="margin-left:10px;padding-top:10px;padding-bottom:10px;font-size:16px;">支付宝支付<text style="padding-left:35px;color:#aaa;font-size:14px;">绿色通道，安全便捷</text>
				<view style="float:right;"><radio /></view>
				</view>
				
			</view>
		
		</view>
		
		
		<view @tap="submit()" style="background:#2C405A;color:#fff;font-size:16px;position:fixed;bottom:0;left:0;right:0;text-align:center;padding:12px;">去付款</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad(op){
			uni.setNavigationBarTitle({title: '我的钱包'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			
		}
	}
</script>

<style>
page {
	background:#eee;
}
</style>
