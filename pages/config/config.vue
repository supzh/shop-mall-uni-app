<template>
	<view style="border-top:1px solid #ddd;">
		<navigator url="../config-account/config-account" hover-class="navigator-hover">
		<view class="f">
				<view class="l">账户信息</view>
				<view class="r">></view>
		</view>
		</navigator>
		
		<view class="f">
			<view class="l">客户电话</view>
			<view class="r"><view style="line-height:20px;padding-top:5px;text-align:right;">4001-180-666<br />周一到周五 9:00-21:30</view></view>
		</view>
		<view class="f">
			<view class="l">版本更新</view>
			<view class="r">当前版本 0.0.1</view>
		</view>
		
		<view class="f" style="text-align:center;font-weight:bold;margin-top:10px;border-top:1px solid #ddd;">
				安全退出
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
			uni.setNavigationBarTitle({title: '设置'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			
		}
	}
</script>

<style>
	.f {float:left;background:#fff;clear:both;width:100%;height:50px;border-bottom:1px solid #ddd;line-height:50px;}
	.l{float:left;padding-left:15px;font-weight:bold;}
	.r{float:right;font-size:14px;color:#999;padding-right:15px;}
	
page {background:#eee;}
</style>
