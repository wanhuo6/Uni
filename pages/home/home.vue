<template>
	<view class="content">
		<button class="marginTop" type="primary" @click="goLayout()">布局</button>
		<button class="marginTop" type="primary" @click="goBanner()">轮播图</button>
		<button class="marginTop" type="primary" @click="goList()">列表</button>
		<button class="marginTop" type="primary" @click="goWidget()">控件</button>
		<button class="marginTop" type="primary" @click="goLayout()">弹窗</button>
		<button class="marginTop" type="primary" @click="goVideo()">视频</button>
		<button class="marginTop" type="primary" @click="goLive()">直播</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello Uni'
			}
		},
		onLoad() {

		},
		methods: {
			goLayout: function() {
				uni.navigateTo({
					url: '/pages/home/lean_view/view_layout/layout'
				});
			},
			goBanner: function() {
				uni.navigateTo({
					url: 'lean_view/view_banner/banner'
				})
			},
			goList: function() {
				uni.navigateTo({
					url: 'lean_view/view_list/list'
				})
			},
			goWidget: function() {
				uni.navigateTo({
					url: 'lean_view/view_widget/widget'
				})
			},
			goVideo: function() {
				uni.navigateTo({
					url: 'lean_view/view_video/video'
				})
			},
			goLive: function() {
				uni.navigateTo({
					url: 'lean_view/view_live/live'
				})
			},
		}
	}
</script>

<style>
	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>