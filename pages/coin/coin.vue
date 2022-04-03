<template>
	<view class="border-top border-light-secondary p-3">
		<view class="rounded py-4 flex flex-column align-center justify-center bg-main">
			<text class="text-white font-sm mb-3">当前金币</text>
			<text class="font-weight-bold text-white" style="font-size: 60rpx;">50</text>
		</view>

		<!-- 分割线 -->
		<view class="border-top border-light-secondary my-3"></view>

		<view>
			<text class="font-sm text-muted">请选择充值金币</text>
		</view>

		<view class="flex flex-wrap" style="margin-left: -20rpx; margin-right: -20rpx;">
			<view class="p-2" style="box-sizing: border-box; width: 33.3%;" v-for="i in 6">
				<view class="flex flex-column align-center justify-center border rounded" style="height: 130rpx;">
					<view class="flex align-center">
						<text class="iconfont text-warning mr-1">&#xe633;</text>
						<text class="font-md font-weight-bold">10</text>
					</view>
					<text class="font text-light-muted">￥10</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		}
	}
</script>

<style lang="less">

</style>
