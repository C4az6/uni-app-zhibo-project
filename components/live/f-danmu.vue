<template>
	<view class="barrage-wrap">
		<scroll-view scroll-y="true" class="pl-3" style="width: 520rpx;height: 300rpx;" scroll-with-animation
			:scroll-into-view="scrollInToView">
			<view :id="`danmu${item.id}`" class="flex align-center rounded p-2 mb-2"
				style="background-color: rgba(255, 255, 255, .125);" v-for="(item) in list" :key="item.id">
				<text class="font text-danger">{{item.name + item.id}}：</text>
				<text class="font text-white">{{item.content + item.id}}</text>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [],
				scrollInToView: ""
			}
		},
		mounted() {},
		methods: {
			// 置于底部
			toBottom(danmu) {
				setInterval(() => {
					let len = this.list.length;
					if (len > 0 && this.list[len - 1]) {
						// 拿到最后一个元素的ID
						if (this.scrollInToView !== 'danmu' + this.list[len - 1].id) {
							console.log('danmu' + this.list[len - 1].id)
							this.scrollInToView = 'danmu' + this.list[len - 1].id
						}
					}
				}, 200)
			},
			// 发送弹幕
			send(danmu) {
				this.list.push(danmu)
				// 置于底部
				this.toBottom(danmu);
			}
		}
	}
</script>

<style lang="less">
	.barrage-wrap {
		position: fixed;
		bottom: 120rpx;
		left: 0;
		right: 0;
		// width: 520rpx;
		height: 300rpx;
	}
</style>
