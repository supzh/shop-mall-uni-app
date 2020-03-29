<template>
	<view style="border-top:1px solid #ddd;">
		
		<view style="color:#fff;background:#DD524D;border-radius:10px;height:120px;margin:10px;">
			<view>
				<view style="float:left;padding:20px;">
					<view style="font-size:22px;">￥20</view>
					<view style="font-size:16px;">订单满199元减20元</view>
				</view>
				
				<view style="float:right;margin:20px;margin-top:30px;background:#fff;color:#DD524D;border-radius:20px;padding:5px;font-size:14px;">
					立即使用
				</view>
				<view style="clear:both;">
					
				</view>
			</view>
			
			<view style="font-size:14px;text-align:center;">有效期：2020.03.01-2021.03.31</view>
			
		</view>
		
		<view style="color:#fff;background:#2C405A;border-radius:10px;height:120px;margin:10px;">
			<view>
				<view style="float:left;padding:20px;">
					<view style="font-size:22px;">￥100</view>
					<view style="font-size:16px;">订单满199元减100元</view>
				</view>
				
				<view style="float:right;margin:20px;margin-top:30px;background:#fff;color:#2C405A;border-radius:20px;padding:5px;font-size:14px;">
					立即使用
				</view>
				<view style="clear:both;">
					
				</view>
			</view>
			
			<view style="font-size:14px;text-align:center;">有效期：2020.03.01-2021.03.31</view>
			
		</view>
		
		<view style="color:#fff;background:orange;border-radius:10px;height:120px;margin:10px;">
			<view>
				<view style="float:left;padding:20px;">
					<view style="font-size:22px;">￥100</view>
					<view style="font-size:16px;">订单满199元减100元</view>
				</view>
				
				<view style="float:right;margin:20px;margin-top:30px;background:#fff;color:#orange;border-radius:20px;padding:5px;font-size:14px;">
					立即使用
				</view>
				<view style="clear:both;">
					
				</view>
			</view>
			
			<view style="font-size:14px;text-align:center;">有效期：2020.03.01-2021.03.31</view>
			
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
			uni.setNavigationBarTitle({title: '优惠券'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
