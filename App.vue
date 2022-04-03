<template>
	<view class="container"></view>
</template>

<script>
	export default {
		data() {
			return {}
		},
		onLaunch() {
			// nvue端加载字体图标
			const domModule = uni.requireNativePlugin('dom')
			domModule.addRule('fontFace', {
				'fontFamily': "iconfont",
				'src': "url('http://at.alicdn.com/t/font_1859985_7mxozsfdvib.ttf')"
			});
			
			// 监听底部导航中间凸起按钮
			uni.onTabBarMidButtonTap(() => {
				console.log('点击了中间按钮~')
			})
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
	/* @import url("/common/animate.min.css"); */
</style>
