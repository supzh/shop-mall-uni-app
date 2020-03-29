<template>
	<view style="border-top:1px solid #ddd;">
		
		<view style="background:#fff;padding:10px;font-size:16px;">
			
			<view style="display:flex;border-bottom:1px solid #ddd;padding-bottom:10px;">
				<view style="background:#eee;height:80px;width:80px;"></view>
				<view style="margin-left:10px;">
					<view style="font-size:14px;">意大利进口面料埃及棉鱼骨纹衬衣</view>
					<view style="padding-top:10px;color:orange;">
						￥7350.00<text style="float:right;color:#666;font-size:14px;">×1</text>
						<br /><text style="padding-top:20px;color:#aaa;font-size:14px;text-decoration: line-through;">吊牌价：14700.00</text>
					</view>
				</view>
			</view>
		</view>
		
		
		<view>
			
			<view style="display:flex;flex-wrap: wrap;padding-left:5px;">
				
				<view class="t">尺寸合身</view>
				
				<view class="t">面料质量好</view>
				
				<view class="t">款式好看</view>
				
				<view class="t">包装精美</view>
				
				<view class="t">尺寸合身</view>
				
				<view class="t">面料质量好</view>
				
			</view>
			<view style="padding:10px;">
			<textarea style="background:#eee;border:1px solid #ddd;border-radius:10px;padding:10px;width:93%;" placeholder="请填写您想说的,说说它的优点和美中不足的地方吧!"></textarea>
			</view>
		</view>
		
	<view @tap="submit()" style="background:#2C405A;color:#fff;font-size:16px;position:fixed;bottom:0;left:0;right:0;text-align:center;padding:12px;">提交</view>
	
	</view>
	
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad(){
			uni.setNavigationBarTitle({title: '发布评价'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			submit(){}
		}
	}
</script>

<style>
.t {font-size:14px;color:#aaa;border:1px solid #ddd;border-radius:20px;padding:5px 10px;margin:5px;}
</style>
