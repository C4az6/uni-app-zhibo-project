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
			<view class="list-item">
				<image class="rounded" src="../../static/demo/1.jpg"></image>
			</view>
			
			<view class="list-item">
				<image class="rounded" src="../../static/demo/1.jpg"></image>
			</view>
			
			
			<view class="list-item">
				<image class="rounded" src="../../static/demo/1.jpg"></image>
			</view>
			
			<view class="list-item">
				<image class="rounded" src="../../static/demo/1.jpg"></image>
			</view>
		
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: '666'
			}
		},
		onLoad() {

		},
		methods: {

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
				width: 375rpx;
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
