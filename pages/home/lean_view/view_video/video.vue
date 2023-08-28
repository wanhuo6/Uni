<template>
	<view class="content">
		<video class="fillWidth" id="myVideo" :src="videoUrl" @error="videoErrorCallback" controls
			poster="https://web-assets.dcloud.net.cn/unidoc/zh/poster.png"
			enable-auto-rotation="enableAutoRotation"></video>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				videoUrl: "https://qiniu-web-assets.dcloud.net.cn/unidoc/zh/2minute-demo.mp4",
				enableAutoRotation: true
			}
		},
		onLoad() {

		},
		methods: {
			videoErrorCallback: function(e) {
				console.log("eeeee", e)
				uni.showModal({
					content: e.target.errMsg,
					showCancel: false
				})
			},
		}
	}
</script>

<style>
</style>