<template>
	<view class="container"></view>
</template>

<script>
	export default {
		data() {
			return {}
		},
		onLaunch() {
			const domModule = uni.requireNativePlugin('dom')
			domModule.addRule('fontFace', {
				'fontFamily': "iconfont",
				'src': "url('http://at.alicdn.com/t/font_1859985_7mxozsfdvib.ttf')"
			});
		}
	}
</script>

<style>
	/*每个页面公共css */
	@import url("/common/free.css");
	@import url("/common/common.css");
	/* #ifndef APP-NVUE */
	/* 不是NVUE端 */
	@import url("/common/icon.css");
	/* #endif */
</style>
