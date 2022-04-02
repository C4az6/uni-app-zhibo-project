<template>
	<view class="page-container">
		<!-- 轮播图部分 -->
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="200">
			<swiper-item>
				<image src="../../static/demo/banner/1.jpg"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/demo/banner/2.jpg"></image>
			</swiper-item>
		</swiper>
		
		<!-- 列表 -->
		<view class="list-wrap">
			<view class="list-item" v-for="i in 6" @click="openLive">
				<image class="rounded" src="../../static/demo/1.jpg" mode="aspectFill"></image>
				<view class="rounded-circle px-2 flex align-center" style="position: absolute;left: 15rpx;top: 15rpx;background-color: rgba(0,0,0,0.4);">
					<text class="iconfont mr-1 iconbizhongguanli text-warning"></text>
					<text class="text-white font">0</text>
				</view>
				
				<view class="rounded-circle px-2 flex align-center" style="position: absolute;right: 15rpx;top: 15rpx;background-color: rgba(0,0,0,0.4);">
					<text class="font-sm text-white">人气：</text>
					<text class="text-white font">0</text>
				</view>
				
				<view class="rounded-circle" style="position: absolute;left: 15rpx;bottom: 15rpx;">
					<text class="text-white font">标题</text>
				</view>
				
				<view class="rounded-circle px-2 flex align-center" style="position: absolute;right: 15rpx;bottom: 15rpx;background-color: rgba(0,0,0,0.4);">
					<text class="rounded-circle bg-danger mr-1" style="width: 20rpx;height: 20rpx;"></text>
					<text class="text-white font-sm">已结束</text>
				</view>
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
		onLoad() {
			this.openLive()
		},
		methods: {
			openLive() {
				uni.navigateTo({
					url:'/pages/live/live'
				})
			}
		}
	}
</script>

<style lang='less'>
	.page-container {
		swiper {
			height: 250rpx;
			swiper-item image {
				width: 750rpx;
				height: 250rpx;
			}
		}
		.list-wrap {
			display: flex;
			flex-wrap: wrap;
			.list-item {
				position: relative;
				width: 375rpx;
				height: 375rpx;
				padding: 5rpx;
				-webkit-box-sizing: border-box;
				-moz-box-sizing: border-box;
				box-sizing: border-box;
				> image {
					width: 365rpx;
					height: 365rpx;
				}
			}
		}
	}
</style>
