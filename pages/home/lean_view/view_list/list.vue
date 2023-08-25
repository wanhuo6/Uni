<template>
	<view class="content">

	</view>
</template>

<script>
	const defaultList = ["河南", "河北", "河流", "河南", "河北", "河流", "河南", "河北", "河流"]
	export default {
		data() {
			return {
				dataList: {},
				loading: false,
				loaded: false
			}
		},
		onLoad() {

		},
		onPullDownRefresh() {
			console.log("下拉动作....");
			uni.showNavigationBarLoading()
			setTimeout(() => {
				uni.hideNavigationBarLoading()
				uni.stopPullDownRefresh()
				this.dataList = defaultList
			}, 1000);

		},
		onReachBottom() {
			console.log("上拉触底事件....");
		},
		methods: {

		}
	}
</script>

<style>

</style>