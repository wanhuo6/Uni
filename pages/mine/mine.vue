<template>
	<view class="content">
		<image class="avatar marginTop centerWidth" :src="avatarUrl"></image>
		<text class="marginTop">昵称33：{{nickName}}</text>
		<button class="marginTop" open-type="chooseAvatar" type="primary" @chooseavatar="changeAvatar">修改头像</button>
		<view class="flex marginTop">
			<text class="centerHeight">修改昵称：</text>
			<input class="nickNameInput " type="nickname" name="nickname" placeholder="请输入昵称" @input="changeNickName"
				v-model="nickName" />
		</view>

	</view>
</template>

<script>
	const defaultAvatarUrl =
		'https://mmbiz.qpic.cn/mmbiz/icTdbqWNOwNRna42FI242Lcia07jQodd2FJGIYQfG0LAJGFxM4FbnQP6yfMxBgJ0F3YRqJCJ1aPAK2dQagdusBZg/0'
	export default {
		data() {
			return {
				nickName: 'Hello  222',
				avatarUrl: defaultAvatarUrl
			}
		},
		onLoad() {
			let name = uni.getStorageSync("nickName")
			let url = uni.getStorageSync("avatarUrl")
			if (url == null || url == "") {
				url = defaultAvatarUrl
			}
			console.log("name", name)
			console.log("url", url);
			this.nickName = name
			this.avatarUrl = url
		},
		methods: {
			changeAvatar(e) {
				let url = e.detail.avatarUrl
				console.log("修改头像", url)
				this.avatarUrl = url;
				uni.setStorageSync("avatarUrl", url)
			},
			changeNickName(e) {
				let name = e.detail.value
				console.log("修改昵称", name)
				this.nickName = name
				uni.setStorageSync("nickName", name)
			}
		}
	}
</script>

<style>
	.avatar {
		overflow: hidden;
		width: 128rpx;
		height: 128rpx;
		border-radius: 50%;
	}

	.avatarBg {
		background-color: aqua;
	}

	.nickNameInput {
		border: 1px solid #f1f1f1;
		padding: 5px;
		width: auto;
	}
</style>