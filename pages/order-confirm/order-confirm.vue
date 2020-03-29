<template>
	<view style="border-top:1px solid #ddd;">
		
		<view style="background:#fff;padding:20px 10px;font-size:16px;">
			还没有填写信息，请点击添加地址
			<text style="float:right;color:#999;">></text>
		</view>
		
		<view style="background:#fff;margin-top:10px;padding:10px;font-size:16px;">
			
			<view style="display:flex;border-bottom:1px solid #ddd;padding-bottom:10px;">
				<view style="background:#eee;height:80px;width:80px;"></view>
				<view style="margin-left:10px;">
					<view style="font-size:14px;">意大利进口面料埃及棉鱼骨纹衬衣</view>
					<view style="padding-top:30px;color:orange;">
						￥7350.00<text style="float:right;color:#666;font-size:14px;">×1</text>
					</view>
				</view>
			</view>
			
			<view>
				<view style="padding-top:10px;color:#555;font-size:16px;">
					查看定制详情
				</view>
				<view style="display:flex;font-size:14px;color:#999;line-height:28px;margin-top:5px;">
					<view>
						类型：标注领<br />
						门襟：平门襟<br />
						版型：标准
					</view>
					
					<view>
						袖型：六角单和<br />
						口袋：无口袋<br />
						绣字位置：无绣字
					</view>
					
				</view>
				
			</view>
			
			
			
		</view>
		
		<view style="margin-top:10px;background:#fff;padding:15px 10px;font-size:16px;">
			
			<view style="float:left;">优惠券</view>
			<view style="float:right;font-size:14px;color:#999;">暂无可用优惠券 ></view>
			<view style="clear:both;"></view>
		</view>
		
		<view style="margin-top:10px;background:#fff;padding:15px 10px;font-size:16px;">
			
			<view style="float:left;">商品合计</view>
			<view style="float:right;font-size:14px;font-weight:bold">￥589.00</view>
			<view style="clear:both;"></view>
			<view style="margin-top:10px;">
			<view style="float:left;">运费</view>
			<view style="float:right;font-size:14px;font-weight:bold">￥0.00</view>
			<view style="clear:both;"></view>
			</view>
			<view style="margin-top:10px;">
			<view style="float:left;">优惠总计</view>
			<view style="float:right;font-size:14px;font-weight:bold">-￥0.00</view>
			<view style="clear:both;"></view>
			</view>
		</view>
		
		<view style="position:fixed;bottom:0;background:#fff;left:0;right:0;height:55px;line-height:55px;padding:0 10px;border-top:1px solid #ddd;">
			
			<view style="float:left;margin-left:25px;color:orange;">￥0.00</view>
			
			<navigator url="../order-pay/order-pay" hover-class="navigator-hover">
				<view style="float:right;background:#2C405A;color:#fff;padding:0 10px;">去付款</view>
			</navigator>
			<view style="clear:both;"></view>
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
			uni.setNavigationBarTitle({title: '完善订单'});
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
