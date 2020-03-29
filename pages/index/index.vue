<template>
	<view style="">
		
		<view style="background:#222;color;#fff;">
			
			<navigator url="../config/config" hover-class="navigator-hover">
			<view>
				
				<view style="float:left;background:#876fe7;border-radius:100%;height:70px;width:70px;margin:10px;"></view>
				<view style="float:left;padding-top:12px;">
					<view style="color:#fff;font-size:16px;">用户昵称</view>
					<view style="margin-top:10px;font-size:14px;color:#fff;line-height:28px;border-radius:30px;border:1px solid #fff;width:70px;text-align:center;">普通会员</view>
				</view>
				<view style="color:#fff;font-size:32px;margin-top:20px;margin-right:10px;float:right;">
					>
				</view>
				<view style="clear:both;"></view>
			</view>
			</navigator>
			
			<view style="clear:both;"></view>
			<view style="margin-top:10px;">
				<view style="background:#f2d39c;color:#6f4d1b;margin:0 10px;border-radius:20px 20px 0 0;">
					<view style="float:left;line-height:60px;margin-left:15px;margin-right:15px;">ico</view>
					<view style="float:left;padding-top:10px;">
						<view style="font-weight:bold;font-size:17px;">钻石会员</view>
						<view style="font-size:14px;">预计可节省3401元/年</view>
					</view>
					<view style="float:right;margin-right:15px;margin-top:15px;background:#222;color:#fff;border-radius:30px;padding:5px 10px;font-size:16px;">ico 开通会员</view>
					<view style="clear:both;"></view>
				</view>
			</view>
		</view>
		
		<view style="display:flex;justify-content:space-around;border:1px solid #ddd;height:70px;">
		
			<navigator url="../wallet-pay/wallet-pay" hover-class="navigator-hover"><view style="border-right:1px solid #ddd;padding-right:60px;padding-top:10px;">
				<text style="font-weight:bold;">0</text><br />
				<text style="font-size:16px;">我的钱包>></text>
			</view>
			</navigator>
			
			<navigator url="../coupon/coupon" hover-class="navigator-hover">
			<view style="padding-top:10px;">
				<text style="font-weight:bold;">0</text><br />
				<text style="font-size:16px;">我的优惠券>></text>
			</view>
			</navigator>
			
		</view>
		
		<view style="border-bottom:1px solid #ddd;height:auto;padding-bottom:15px;">
				<view>
					<view style="padding:10px;font-size:16px;float:left;">我的订单</view>
					<navigator url="../order-list/order-list" hover-class="navigator-hover"><view style="float:right;padding:10px;font-size:12px;color:#999;padding-top:20px;">全部></view></navigator>
					<view style="clear:both;"></view>
				</view>
				<view style="display:flex;justify-content: space-around;text-align:center;">
					<navigator url="../order-list/order-list" hover-class="navigator-hover"><view style="width:60px;">
						<view style="background:#fff;height:50px;color:#6f4d1b;line-height:50px;">image</view>
						<view style="font-size:14px;">待上门</view>
					</view></navigator>
					<navigator url="../order-list/order-list" hover-class="navigator-hover"><view style="width:60px;">
						<view style="background:#fff;height:50px;color:#6f4d1b;line-height:50px;">image</view>
						<view style="font-size:14px;">待支付</view>
					</view></navigator>
					<navigator url="../order-list/order-list" hover-class="navigator-hover"><view style="width:60px;">
						<view style="background:#fff;height:50px;color:#6f4d1b;line-height:50px;">image</view>
						<view style="font-size:14px;">待收货</view>
					</view></navigator>
					<navigator url="../order-list/order-list" hover-class="navigator-hover"><view style="width:60px;">
						<view style="background:#fff;height:50px;color:#6f4d1b;line-height:50px;">image</view>
						<view style="font-size:14px;">待评价</view>
					</view></navigator>
					<navigator url="../order-list/order-list" hover-class="navigator-hover"><view style="width:60px;">
						<view style="background:#fff;height:50px;color:#6f4d1b;line-height:50px;">image</view>
						<view style="font-size:14px;">售后</view>
					</view></navigator>
					
					
					
				</view>
			
		</view>
		
		<view style="border-bottom:1px solid #ddd;height:auto;padding-bottom:15px;">
				<view>
					<view style="padding:10px;font-size:16px;float:left;">我的服务</view>
					<view style="clear:both;"></view>
				</view>
				<view style="display:flex;flex-wrap:wrap;justify-content: left;text-align:center;">
					<view style="width:80px;margin:5px;">
						<view style="background:#fff;height:50px;color:#222;line-height:50px;">image</view>
						<view style="font-size:14px;">我的地址</view>
					</view>
					<view style="width:80px;margin:5px;">
						<view style="background:#fff;height:50px;color:#222;line-height:50px;">image</view>
						<view style="font-size:14px;">私人顾问</view>
					</view>	<view style="width:80px;margin:5px;">
						<view style="background:#fff;height:50px;color:#222;line-height:50px;">image</view>
						<view style="font-size:14px;">形象报告</view>
					</view>	<view style="width:80px;margin:5px;">
						<view style="background:#fff;height:50px;color:#222;line-height:50px;">image</view>
						<view style="font-size:14px;">服务帮助</view>
					</view>
					<view style="width:80px;margin:5px;">
						<view style="background:#fff;height:50px;color:#222;line-height:50px;">image</view>
						<view style="font-size:14px;">企业定制</view>
					</view>
					<navigator url="../feedback/feedback" hover-class="navigator-hover">
						<view style="width:80px;margin:5px;">
							<view style="background:#fff;height:50px;color:#222;line-height:50px;">image</view>
							<view style="font-size:14px;">意见反馈</view>
						</view>
					</navigator>	
					<view style="width:80px;margin:5px;">
						<view style="background:#fff;height:50px;color:#222;line-height:50px;">image</view>
						<view style="font-size:14px;">关于我们</view>
					</view>
					
					
					
					
					
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
		methods: {

		}
	}
</script>

<style>

</style>
