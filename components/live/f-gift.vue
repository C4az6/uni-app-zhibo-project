<template>

	<list class="gift-content" show-scrollbar="false">
		<cell :ref="`item${index}`" v-for="(item, index) in gifts" key="index" insert-animation="default"
			delete-animation="default">
			<view class="flex align-center px-3 my-3">
				<!-- 左侧 -->
				<view class="user-info-content p bg-gradient rounded-circle flex align-center">
					<view class="p">
						<image class="rounded-circle" :src="item.avatar || '../../static/avatar/881406830_im.jpg'"
							style="width: 70rpx;height: 70rpx;" mode=""></image>
					</view>
					<view class="flex-1 flex-column justify-center">
						<text class="text-white font">{{item.username}}</text>
						<text class="text-white font-sm">送 {{item.gift_name}}</text>
					</view>
					<view class="p">
						<image class="rounded-circle" :src="item.gift_image || '../../static/gift/1.png'"
							style="width: 70rpx;height: 70rpx;" mode=""></image>
					</view>
				</view>

				<!-- 右侧送出礼物数量 -->
				<text class="text-warning font-lg ml-1">X {{item.num}}</text>
			</view>
		</cell>
	</list>

</template>

<script>
	const dom = weex.requireModule('dom');
	export default {
		data() {
			return {
				// 礼物列表
				gifts: []
			}
		},
		methods: {
			// 送礼物
			send(gift) {
				this.gifts.push(gift)
				this.toBottom()
				this.autoHide()
			},
			// 置于底部
			toBottom() {
				this.$nextTick(() => {
					let index = this.gifts.length - 1;
					let ref = 'item' + index
					if (this.$refs[ref]) {
						dom.scrollToElement(this.$refs[ref][0], {
							animated: true
						})
					}
				})
			},
			// 自动消失
			autoHide() {
				if (this.gifts.length) {
					let timer = setTimeout(() => {
						this.gifts.splice(0, 1)
					}, 5000)
				}
			}
		}
	}
</script>

<style lang="less">
	.bg-gradient {
		background-image: linear-gradient(to right, #BCABB1, #65AAF0);
	}

	.gift-content {
		width: 520rpx;
		height: 500rpx;

		.user-info-content {
			display: flex;
			width: 325rpx;
		}
	}
</style>
