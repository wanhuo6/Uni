<template>
	<view class="content">
		<text class="center_width marginTop">横向布局</text>
		<view class="flex marginTop" style="flex-direction: row;">
			<text class="center_width">条目1</text>
			<text class="center_width">条目2</text>
			<text class="center_width">条目3</text>
		</view>
		<text class="center_width marginTop">纵向布局</text>
		<view class="flex marginTop" style="flex-direction: column;">
			<text class="center_width">条目1</text>
			<text class="center_width marginTop">条目2</text>
			<text class="center_width marginTop">条目3</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello  layout'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
</style>