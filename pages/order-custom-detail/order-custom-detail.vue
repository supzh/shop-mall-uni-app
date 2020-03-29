<template>
	<view>
		
		<view style="position:fixed;bottom:0;left:0;right:0;font-size:16px;background:#fff;text-align:center;height:50px;line-height:50px;color:#555;">取消订单</view>
		

		
		<view style="margin-top:10px;background:#fff;">
			
			<view>
				<view style="float:left;margin:10px;">
					<view style="width:70px;line-height:70px;text-align:center;height:70px;font-size:12px;background:#2C405A;color:#fff;">上门量体</view>
				</view>
				<view style="float:left;font-size:13px;padding-top:10px;line-height:23px;">
					【夹克】140293/203 宝蓝色素色 100%麻<br />
					<text style="color:red;">￥3920.00</text><text style="color:#999;">【夹克】</text><br />
				
				</view>
				<view style="clear:both;"></view>
			</view>
		</view>
		
		<view style="margin-top:10px;background:#fff;">
			<view style="color:#666;padding:10px;font-size:16px;border-bottom:1px dotted #ddd;">面料及工艺</view>
			<view>
				
				<view>
					<view>image</view>
					<view>G20122317</view>
				</view>
				
			</view>
		</view>
		
		<view style="z-index:999;position:fixed;bottom:0;background:#fff;left:0;right:0;height:55px;line-height:55px;padding:0 10px;border-top:1px solid #ddd;">
			
			sfdsdf
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
			uni.setNavigationBarTitle({title: '定制详情'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			
		}
	}
</script>

<style>
page {background:#eee;}
</style>
