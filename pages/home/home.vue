<template>
	<view class="content">
		<button class="marginTop" type="primary" @click="goLayout()">布局</button>
		<button class="marginTop" type="primary" @click="goBanner()">轮播图</button>
		<button class="marginTop" type="primary" @click="goList()">列表</button>
		<button class="marginTop" type="primary" @click="goWidget()">控件</button>
		<button class="marginTop" type="primary" @click="goDailog()">弹窗</button>
		<button class="marginTop" type="primary" @click="goVideo()">视频</button>
		<button class="marginTop" type="primary" @click="goLive()">直播</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				//title: 'Hello Uni'
			}
		},
		onLoad() {

		},
		methods: {
			goLayout() {
				uni.navigateTo({
					url: '/pages/home/lean_view/view_layout/layout'
				});
			},
			goBanner() {
				uni.navigateTo({
					url: 'lean_view/view_banner/banner'
				})
			},
			goList() {
				uni.navigateTo({
					url: 'lean_view/view_list/list'
				})
			},
			goDailog() {
				uni.showModal({
					title: '提示',
					content: '确定要退出吗',
					success(res) {
						if (res.confirm) {
							uni.showToast({
								title: '成功',
								icon: 'success',
								duration: 2000
							})
						} else if (res.cancel) {
							uni.showToast({
								title: '取消',
								icon: 'error',
								duration: 2000
							})
						}
					}

				})
			},
			goWidget() {
				uni.navigateTo({
					url: 'lean_view/view_widget/widget'
				})
			},
			goVideo() {
				uni.navigateTo({
					url: 'lean_view/view_video/video'
				})
			},
			goLive() {
				uni.navigateTo({
					url: 'lean_view/view_live/live'
				})
			},
		}
	}
</script>

<style>
</style>