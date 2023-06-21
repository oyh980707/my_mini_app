<template>
	<view class="content">
		<image class="logo" src="/static/home.png"></image>
		<view>
			<text class="title">{{title}}</text>
		</view>
		<hgr-tabbar :current-page="0"></hgr-tabbar>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: '光蕊的工作室'
			}
		},
		onLoad() {
			console.log('App onLoad')
		},
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
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
		margin: 200rpx auto 50rpx auto;
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