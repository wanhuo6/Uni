<template>
	<view class="content">
		<button class="marginTop" type="primary" loading="true">按钮</button>
		<button class="marginTop" type="primary" loading="true" plain="true">按钮</button>
		<button class="marginTop" type="primary" loading="true" plain="false" disabled="true">按钮</button>
		<button class="marginTop" type="primary" plain="true" disabled="false">按钮</button>
		<radio-group class="marginTop">
			<label class="radio">
				<radio value="r1" checked="true" />A
			</label>
			<label class="radio marginLeft">
				<radio value="r2" />B
			</label>
		</radio-group>
	</view>

</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello  widget'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>