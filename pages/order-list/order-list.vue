<template>
	<view>
		<view style="display:flex;justify-content: space-around;background:#fff;font-size:14px;line-height:32px;color:#555;">
			<view class="act">全部订单</view>
			<view>待上门</view>
			<view>待支付</view>
			<view>待收货</view>
			<view>待评价</view>
			
		</view>
		
		<view style="margin:10px;">
			<navigator url="../order-detail/order-detail" hover-class="navigator-hover">
			<view style="background:#fff;padding-bottom:5px;">
				
				<view style="padding:10px;font-size:14px;border-bottom:1px dotted #ddd;">下单时间：2020-04-02 20:16:01</view>
				
				<view>
					<view style="float:left;margin:10px;">
						<view style="width:70px;line-height:70px;text-align:center;height:70px;font-size:12px;background:#2C405A;color:#fff;">上门量体</view>
					</view>
					<view style="float:left;font-size:14px;padding-top:10px;line-height:23px;">
						预约编号：DD12803726<br />
						预约状态：等待预约确认<br />
						量体时间：<text style="color:#007AFF">等待客服确认</text>
					</view>
					<view style="clear:both;"></view>
				</view>
				
				<view style="background:#eee;margin:10px;font-size:14px;color:#999;padding:6px 10px;">
					包含商品：夹克×1
				</view>
			</view></navigator>
			<navigator url="../order-detail/order-detail" hover-class="navigator-hover">
			<view style="background:#fff;padding-bottom:5px;border-top:1px solid #ddd;">
				
				<view style="padding:10px;font-size:14px;border-bottom:1px dotted #ddd;">下单时间：2020-04-02 20:16:01</view>
				
				<view>
					<view style="float:left;margin:10px;">
						<view style="width:70px;line-height:70px;text-align:center;height:70px;font-size:12px;background:#2C405A;color:#fff;">上门量体</view>
					</view>
					<view style="float:left;font-size:14px;padding-top:10px;line-height:23px;">
						预约编号：DD12803726<br />
						预约状态：等待预约确认<br />
						量体时间：<text style="color:#007AFF">等待客服确认</text>
					</view>
					<view style="clear:both;"></view>
				</view>
				
				<view style="background:#eee;margin:10px;font-size:14px;color:#999;padding:6px 10px;">
					包含商品：夹克×1
				</view>
			</view>
			</navigator>
			
		<navigator url="../order-detail/order-detail" hover-class="navigator-hover">
		<view style="background:#fff;padding-bottom:5px;border-top:1px solid #ddd;">
			
			<view style="padding:10px;font-size:14px;border-bottom:1px dotted #ddd;">下单时间：2020-04-02 20:16:01</view>
			
			<view>
				<view style="float:left;margin:10px;">
					<view style="width:70px;line-height:70px;text-align:center;height:70px;font-size:12px;background:#2C405A;color:#fff;">上门量体</view>
				</view>
				<view style="float:left;font-size:14px;padding-top:10px;line-height:23px;">
					预约编号：DD12803726<br />
					预约状态：等待预约确认<br />
					量体时间：<text style="color:#007AFF">等待客服确认</text>
				</view>
				<view style="clear:both;"></view>
			</view>
			
			<view style="background:#eee;margin:10px;font-size:14px;color:#999;padding:6px 10px;">
				包含商品：夹克×1
			</view>
		</view>
		</navigator>
			
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
			uni.setNavigationBarTitle({title: '我的订单'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			
		}
	}
</script>

<style>
	.act {border-bottom:3px solid #2C405A;font-weight:bold;color:#333;}
page {background:#eee;}
</style>
