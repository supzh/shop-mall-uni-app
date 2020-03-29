<template>
	<view>
		<navigator url="../compose-detail/compose-detail" hover-class="navigator-hover">
			<view class="f">image</view>
		</navigator>
		<navigator url="../compose-detail/compose-detail" hover-class="navigator-hover">
			<view class="f">image</view>
		</navigator>
		<navigator url="../compose-detail/compose-detail" hover-class="navigator-hover">
			<view class="f">image</view>
		</navigator>
		<navigator url="../compose-detail/compose-detail" hover-class="navigator-hover">
			<view class="f">image</view>
		</navigator>
		<navigator url="../compose-detail/compose-detail" hover-class="navigator-hover">
			<view class="f">image</view>
		</navigator>
		<navigator url="../compose-detail/compose-detail" hover-class="navigator-hover">
			<view class="f">image</view>
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
			uni.setNavigationBarTitle({title: '搭配LOOK'});
			uni.setNavigationBarColor({frontColor: '#000000',backgroundColor: '#fff'});
		},
		methods: {
			
		}
	}
</script>

<style>
.f {text-align:center;margin:10px;background:#eee;height:400px;line-height:400px;color:#555;}
</style>
