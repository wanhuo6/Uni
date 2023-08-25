<template>
	<view class="content">
		</image>
		<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval"
			:duration="duration">
			<block v-for="(item,index) in bannerList" :key="index">
				<swiper-item>
					<image class="fillWidth" mode="widthFix" :src="item"></image>
				</swiper-item>
			</block>
		</swiper>
		<view class="marginTop">
			<text class="marginLeft">指示点2</text>
			<switch class="marginLeft" checked="indicatorDots" @change="changeIndicatorDots"></switch>
		</view>
		<view class="marginTop">
			<text class="marginLeft">自动播放</text>
			<switch class="marginLeft" checked="autoplay" @change="changeAutoPlay"></switch>
		</view>
		<view class="marginTop">
			<text class="marginLeft">幻灯片时长：{{duration}}</text>
			<slider @change="changeDuration" :value="duration" min="500" max="2000"></slider>
		</view>
		<view class="marginTop">
			<text class="marginLeft">自动播放时长：{{interval}}</text>
			<slider @change="changeInteral" :value="interval" min="2000" max="10000"></slider>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello  banner',
				bannerList: ["https://img2.baidu.com/it/u=2048195462,703560066&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=333",
					"https://img0.baidu.com/it/u=1435639120,2241364006&fm=253&fmt=auto&app=138&f=JPEG?w=800&h=500",
					"https://img0.baidu.com/it/u=4187423482,206374644&fm=253&fmt=auto&app=120&f=JPEG?w=1280&h=800"
				],
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500
			}
		},
		onLoad() {

		},
		methods: {
			changeIndicatorDots(e) {
				this.indicatorDots = !this.indicatorDots
			},
			changeAutoPlay(e) {
				this.autoplay = !this.autoplay
			},
			changeInteral(e) {
				this.interval = e.detail.value
			},
			changeDuration(e) {
				this.duration = e.detail.value
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