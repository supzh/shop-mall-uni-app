<template>
	<view style="padding-bottom:75px;">
		
		
		<view style="background:#222;height:150px;">
			
			<view style="float:right;padding:20px;color:#fff;padding-top:40px;">
				<view style="font-size:28px;">限时秒杀</view>
				<view style="margin-top:10px;padding-left:10px;border-left:3px solid #f2d39c">限量精品 低至5.5折</view>
			</view>
				
		</view>
		
		<view style="background:#fff;display:flex;border-radius:10px 10px 0 0;height:58px;justify-content: space-around;">
			<view style="color:#a57a40;text-align:center;font-size:14px;height:50px;padding-top:6px;border-bottom:3px solid #a57a40">15:00<br />即将开始</view>
			
			<view style="color:#999;text-align:center;font-size:14px;height:50px;padding-top:6px;border-bottom:3px solid #fff">15:00<br />明日预告</view>
		</view>
		
		<view style="background:#2C405A;margin:10px;border-radius:50px;font-size:15px;line-height:50px;padding-left:15px;color:#fff;text-align:center;">
			距开始还有 00：40：41
			</view>
			<view style="display:flex;flex-direction:row;background:#fff;margin:10px;box-shadow:1px 1px 2px #ccc;">
				
				<view style="line-height:120px;padding:10px;"> <checkbox value="cb" checked="true" /> </view>
				
				<view>
					
					<view style="width:70px;height:110px;border:1px solid #ddd;margin-top:15px;color:#ccc;text-align:center;line-height:110px;">image</view>
					
				</view>
				
				<view style="margin-left:10px;display:flex;flex-direction: column;padding-bottom:10px;padding-right:10px;">
					<view style="font-size:16px;margin-top:10px;">意大利进口面料埃及棉鱼骨纹衬衣</view>
					<view style="font-size:14px;color:#333;background:#f2d39c;width:80px;border-radius:5px;text-align:center;margin-top:10px;">仅剩3件</view>
					<view style="color:#f2d39c;background:#fff;width:100%;margin-top:15px;line-height:20px;"><text style="font-size:14px;color:#222;">秒杀价：</text>￥7350.00<br /><text style="color:#ccc;font-size:14px;text-decoration: line-through;">￥10000.00</text></view>
					<view style="align-self:flex-end;margin-top:-20px;font-size:16px;background:#f2d39c;padding:5px;border-radius:10px;font-weight:bold;">开抢提醒</view>
					<view style="align-self:flex-end;color:#ccc;font-size:12px;">659人已设置提醒</view>
				</view>
				
			</view>
			
			<view style="display:flex;flex-direction:row;background:#fff;margin:10px;box-shadow:1px 1px 2px #ccc;">
				
				<view style="line-height:120px;padding:10px;"> <checkbox value="cb" checked="true" /> </view>
				
				<view>
					
					<view style="width:70px;height:110px;border:1px solid #ddd;margin-top:15px;color:#ccc;text-align:center;line-height:110px;">image</view>
					
				</view>
				
				<view style="margin-left:10px;display:flex;flex-direction: column;padding-bottom:10px;padding-right:10px;">
					<view style="font-size:16px;margin-top:10px;">意大利进口面料埃及棉鱼骨纹衬衣</view>
					<view style="font-size:14px;color:#333;background:#f2d39c;width:80px;border-radius:5px;text-align:center;margin-top:10px;">仅剩3件</view>
					<view style="color:#f2d39c;background:#fff;width:100%;margin-top:15px;line-height:20px;"><text style="font-size:14px;color:#222;">秒杀价：</text>￥7350.00<br /><text style="color:#ccc;font-size:14px;text-decoration: line-through;">￥10000.00</text></view>
					<view style="align-self:flex-end;margin-top:-20px;font-size:16px;background:#f2d39c;padding:5px;border-radius:10px;font-weight:bold;">开抢提醒</view>
					<view style="align-self:flex-end;color:#ccc;font-size:12px;">659人已设置提醒</view>
				</view>
				
			</view>
			
			<view style="display:flex;flex-direction:row;background:#fff;margin:10px;box-shadow:1px 1px 2px #ccc;">
				
				<view style="line-height:120px;padding:10px;"> <checkbox value="cb" checked="true" /> </view>
				
				<view>
					
					<view style="width:70px;height:110px;border:1px solid #ddd;margin-top:15px;color:#ccc;text-align:center;line-height:110px;">image</view>
					
				</view>
				
				<view style="margin-left:10px;display:flex;flex-direction: column;padding-bottom:10px;padding-right:10px;">
					<view style="font-size:16px;margin-top:10px;">意大利进口面料埃及棉鱼骨纹衬衣</view>
					<view style="font-size:14px;color:#333;background:#f2d39c;width:80px;border-radius:5px;text-align:center;margin-top:10px;">仅剩3件</view>
					<view style="color:#f2d39c;background:#fff;width:100%;margin-top:15px;line-height:20px;"><text style="font-size:14px;color:#222;">秒杀价：</text>￥7350.00<br /><text style="color:#ccc;font-size:14px;text-decoration: line-through;">￥10000.00</text></view>
					<view style="align-self:flex-end;margin-top:-20px;font-size:16px;background:#f2d39c;padding:5px;border-radius:10px;font-weight:bold;">开抢提醒</view>
					<view style="align-self:flex-end;color:#ccc;font-size:12px;">659人已设置提醒</view>
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
		onLoad(){
			uni.setNavigationBarTitle({title: '限时秒杀'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			
		}
	}
</script>

<style>
page {background:#eee;}
	
</style>
