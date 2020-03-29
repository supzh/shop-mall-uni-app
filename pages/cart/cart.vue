<template>
	<view style="border-top:1px solid #ddd;padding-bottom:75px;">
		
		
		<view style="position:fixed;bottom:0;background:#fff;left:0;right:0;height:55px;line-height:55px;padding:0 10px;border-top:1px solid #ddd;">
			
			<view style="float:left;"> <checkbox value="cb" checked="true" /> 全选</view>
			<view style="float:left;margin-left:25px;">合计：￥0.00</view>
			
			<navigator url="../order-confirm/order-confirm" hover-class="navigator-hover">
				<view style="float:right;background:#2C405A;color:#fff;padding:0 10px;">去结算</view>
			</navigator>
			<view style="clear:both;"></view>
		</view>
		
		<view style="background:#fff;">
			
			<view>
				<view style="float:left;margin-top:10px;margin-left:10px;line-height:80px;margin-right:5px;">
					<checkbox value="cb" checked="true" />
				</view>
				<view style="float:left;margin-right:10px;">
					<view style="font-size:10px;height:70px;border:1px solid #ddd;margin-top:10px;margin-bottom:10px;text-align:center;line-height:70px;color:orange;">image</view>
					<view style="font-size:12px;border:1px solid #ddd;padding:5px;border-radius:3px;color:#999;margin-bottom:10px;">调整细节</view>
				</view>
				<view style="float:left;margin-top:7px;">
					<view style="font-size:14px;">意大利进口面料埃及棉鱼骨纹衬衣</view>
					<view style="font-size:12px;color:#aaa;margin-top:5px;">100%羊毛</view>
					<view style="color:orange;font-size:14px;margin-top:15px">￥7350.00</view>
					<view style="position:absolute;right:20px;">  <input style="border:1px solid #ddd;width:30px;text-align:center;border-radius:5px;" value="1" /></view>
				</view>
				<view style="clear:both;"></view>
			</view>
			
			<view style="border-top:1px solid #ddd;">
				<view style="float:left;margin-top:10px;margin-left:10px;line-height:80px;margin-right:5px;">
					<checkbox value="cb" checked="true" />
				</view>
				<view style="float:left;margin-right:10px;">
					<view style="font-size:10px;height:70px;border:1px solid #ddd;margin-top:10px;margin-bottom:10px;text-align:center;line-height:70px;color:orange;">image</view>
					<view style="font-size:12px;border:1px solid #ddd;padding:5px;border-radius:3px;color:#999;margin-bottom:10px;">调整细节</view>
				</view>
				<view style="float:left;margin-top:7px;">
					<view style="font-size:14px;">意大利进口面料埃及棉鱼骨纹衬衣</view>
					<view style="font-size:12px;color:#aaa;margin-top:5px;">100%羊毛</view>
					<view style="color:orange;font-size:14px;margin-top:15px">￥7350.00</view>
					<view style="position:absolute;right:20px;">  <input style="border:1px solid #ddd;width:30px;text-align:center;border-radius:5px;" value="1" /></view>
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
		onLoad() {
			uni.setNavigationBarTitle({title: '购物袋'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			
		}
	}
</script>

<style>
page {background:#eee}
</style>
