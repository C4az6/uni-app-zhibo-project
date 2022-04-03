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

		<!-- 金币选择列表 -->
		<view class="flex flex-wrap" style="margin-left: -20rpx; margin-right: -20rpx;">
			<view class="p-2" style="box-sizing: border-box; width: 33.3%;" v-for="(item, index) in coinList"
				:key="item.coin">
				<view v-if="item.price > 0" class="flex flex-column align-center justify-center border rounded"
					style="height: 130rpx;" @click="coinSelectClick(index)"
					:class="activeIndex === index ? 'border-main' : ''">
					<view class="flex align-center">
						<text class="iconfont text-warning mr-1">&#xe633;</text>
						<text class="font-md font-weight-bold">{{item.coin}}</text>
					</view>
					<text class="font text-light-muted">￥{{item.price}}</text>
				</view>

				<view v-else class="flex flex-column align-center justify-center border rounded" style="height: 130rpx;"
					@click="customCoin">
					<text class="font-md text-light-muted">自定义</text>
				</view>
			</view>
		</view>

		<!-- 底部操作条 -->
		<view class="position-fixed left-0 right-0 bottom-0 border-top flex align-center px-3" style="height: 100rpx;">
			<view class="flex align-center">
				<text class="iconfont text-warning mr-1">&#xe633;</text>
				<text class="font-md font-weight-bold">{{payPrice}}</text>
			</view>

			<view class="bg-main rounded flex align-center justify-center ml-auto" style="width: 150rpx;height: 70rpx;">
				<text class="font-md text-white">去充值</text>
			</view>
		</view>


		<!-- 充值弹出框 -->
		<uni-popup ref="inputDialog" type="dialog">
			<uni-popup-dialog mode="input" title="输入金额" placeholder="充值金额" inputType="number"
				@confirm="dialogInputConfirm" @close="close"></uni-popup-dialog>
		</uni-popup>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				coinList: [{
						coin: 10,
						price: 10
					},
					{
						coin: 20,
						price: 20
					},
					{
						coin: 30,
						price: 30
					},
					{
						coin: 50,
						price: 50
					},
					{
						coin: 100,
						price: 100
					},
					{
						price: 0
					}
				],
				// 选中的充值列表项
				activeIndex: 0,
				// 充值金额
				payPrice: 0
			};
		},
		methods: {
			// 关闭充值金币弹出层
			close() {
				console.log('关闭.')
			},
			// 自定义充值金额弹出层确认按钮
			dialogInputConfirm(val) {
				if (!val) {
					return uni.showToast({
						title: '请输入要充值的金额',
						icon: 'none'
					})
				}
				this.payPrice = val;
			},
			// 自定义充值金额
			customCoin() {
				this.$refs.inputDialog.open()
			},
			// 充值金币列表切换
			coinSelectClick(index) {
				this.activeIndex = index;
				if (this.coinList[index].price > 0) {
					this.payPrice = this.coinList[index].price
				}
			}
		},
		onLoad() {
			let p = this.coinList[this.activeIndex].price;
			(p > 0) && (this.payPrice = p)
		}
	}
</script>

<style lang="less">

</style>
