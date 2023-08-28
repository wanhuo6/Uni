<template>
	<view class="content">
		<text>网络请求测试</text>
		<text>结果：{{netResult}}</text>
		<swiper class="swiper marginTop" circular :indicator-dots="indicatorDots" :autoplay="autoplay"
			:interval="interval" :duration="duration">
			<block v-for="(item,index) in bannerList" :key="index">
				<swiper-item>
					<image class="fillWidth" mode="widthFix" :src="item.imagePath"></image>
				</swiper-item>
			</block>
		</swiper>
		<button class="marginTop" type="primary" @click="getRequest()">发起请求</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isLoading: false,
				buttonEnable: true,
				netResult: '',
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				bannerList: []
			}
		},
		onLoad() {

		},
		methods: {
			getRequest() {
				this.isLoading = true
				this.buttonEnable = false
				uni.request({
					url: "https://www.wanandroid.com/banner/json",
					method: "GET",
					success: (result) => {
						console.log("request success result:" + result)
						uni.showToast({
							title: "请求成功",
							icon: "success",
							mask: true,
							duration: 1000
						})
						this.bannerList = result.data.data
						this.isLoading = false
						this.buttonEnable = true
						this.netResult = result.errMsg
					},
					fail: (errMsg) => {
						uni.showToast({
							title: "请求失败",
							icon: "error",
							mask: true,
							duration: 1000
						})
						this.bannerList = []
						this.isLoading = false
						this.buttonEnable = true
						this.netResult = errMsg
					}
				})
			}
		}
	}
</script>

<style>
	.swiper {
		height: 350rpx;
		width: 100%;
	}
</style>