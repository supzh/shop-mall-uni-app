<template>
	<view>
		
		<view style="position:fixed;bottom:0;left:0;right:0;font-size:16px;background:#fff;text-align:center;height:50px;line-height:50px;color:#555;">取消订单</view>
		
		<view style="margin-top:10px;background:#fff;">
			<view style="padding:10px;font-weight:bold;font-size:16px;">收货人信息</view>
			
			<view style="font-size:16px;padding:5px 10px;color:#666;">孙震 16630011857</view>
			<view style="font-size:16px;padding:5px 10px;color:#666;">收货地址：福建省厦门市湖里区地址</view>
		</view>
		
		<view style="margin-top:10px;background:#fff;">
			<view>
				<view style="float:left;margin:10px;">
					<view style="width:70px;line-height:70px;text-align:center;height:70px;font-size:12px;background:#2C405A;color:#fff;">上门量体</view>
				</view>
				<view style="float:left;font-size:13px;padding-top:10px;line-height:23px;">
					<text style="background:black;color:#fff;width:35px;padding:0 2px;font-size:12px;text-align:center;border-radius:2px;">精品</text>【夹克】140293/203 宝蓝色素色 100%麻<br />
					<text style="color:red;">￥3920.00</text><br />
					<text style="float:right;">×1</text><br />
					<navigator url="../order-custom-detail/order-custom-detail" hover-class="navigator-hover"><text style="float:right;color:#2C405A;padding-bottom:10px;">定制详情</text></navigator>
				</view>
				<view style="clear:both;"></view>
			</view>
		</view>
		
		<view style="margin-top:10px;background:#fff;padding:10px 0;">
			
			<view style="font-size:14px;padding:2px 10px;color:#666;">预约编号：DD12803726 &nbsp;&nbsp;&nbsp; <text style="background:#fff;color:#666;width:35px;padding:0 2px;font-size:12px;text-align:center;border-radius:2px;border:1px solid #666;">复制</text></view>
			<view style="font-size:14px;padding:2px 10px;color:#666;">下单时间：2020-04-02 20:16:01</view>
			<view style="font-size:14px;padding:2px 10px;color:#666;">预约状态：等待预约确认</view>
			<view style="font-size:14px;padding:2px 10px;color:#666;">量体时间：等待客服确认</view>
			<view style="font-size:14px;padding:2px 10px;color:#666;">量体顾问：等待分配</view>
		</view>
		
		<navigator url="../order-appraise/order-appraise" hover-class="navigator-hover">
			<view style="font-size:14px;background:#fff;margin-top:10px;text-align:center;height:50px;line-height:50px;color:#555;">发布评价</view>
		</navigator>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad(){
			uni.setNavigationBarTitle({title: '预约详情'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			
		}
	}
</script>

<style>
page {background:#eee;}
</style>
