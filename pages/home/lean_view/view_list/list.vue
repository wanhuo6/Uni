<template>
	<view class="content">
		<view v-for="(item,index) in dataList" :key="index">
			<view class="item">
				<text class="item_text centerParent" style="color: white; ">条目：{{item}}</text>
			</view>
		</view>
	</view>
</template>

<script>
	const defaultList = ["河南", "河北", "河流", "河南", "河北", "河流", "河南", "河北", "河流"]
	const defaultList2 = ["河南", "河北", "河流", "河南", "河北", "河流", "河南", "河北", "河流", "dsf dfsdf s发多少", "水电费第三方"]
	export default {
		data() {
			return {
				dataList: {},
				loading: false,
				loaded: false
			}
		},
		onPullDownRefresh() {
			console.log("下拉动作3....");
			uni.showNavigationBarLoading()
			setTimeout(() => {
				uni.hideNavigationBarLoading()
				uni.stopPullDownRefresh()
				this.dataList = defaultList
			}, 1000);

		},
		onReachBottom() {
			console.log("上拉触底事件....");
			uni.showLoading({
				title: "加载中...",
			})
			setTimeout(() => {
				this.dataList = defaultList2
				uni.hideLoading()
			}, 1000)

		},
		onLoad() {

		},

		methods: {

		}
	}
</script>

<style>
	.item {
		margin: 20rpx;
		background-color: coral;
		height: 300rpx;
		display: flex;
		border-radius: 20rpx;
	}

	.item_text {
		height: auto;
	}
</style>