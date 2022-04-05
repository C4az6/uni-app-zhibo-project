<template>
	<view>
		<view class="flex align-center">
			<view style="width: 180rpx;height: 180rpx;" class="flex align-center justify-center">
				<image class="rounded-circle" style="width: 105rpx;height: 105rpx;"
					src="../../static/avatar/881406830_im.jpg" mode=""></image>
			</view>
			<view class="flex flex-1 flex-column justify-center" style="height: 180rpx;">
				<text class="font-md">猪猪侠</text>
				<text class="font text-muted">一个前端开发</text>
			</view>
			<view class="border rounded flex  border-main p-2 mr-3" hover-class="bg-light">
				<text class="text-main font">编辑资料</text>
			</view>
		</view>
		<view class="f-divider"></view>
		
		<f-list-item icon="iconliwu" title="我的金币" :showRight="false">
			<text text class="text-muted font">50币 点击充值</text>
		</f-list-item>
		
		<f-list-item icon="iconliwu" title="我的直播">
			<text text class="text-muted font">0</text>
		</f-list-item>
		
		<f-list-item icon="iconliwu" title="我的关注">
			<text text class="text-muted font">50币 </text>
		</f-list-item>
		
		<f-list-item icon="iconliwu" title="历史记录">
		</f-list-item>

	</view>
</template>

<script>
	import fListItem from '@/components/common/f-list-item.vue';
	export default {
		components: {
			fListItem
		},
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style lang="less">

</style>
