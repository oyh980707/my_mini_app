<template>
	<view class="content">
		<image class="logo" src="/static/mine.png"></image>
		<view>
			<text class="title">{{title}}</text>
		</view>
	</view>
</template> 

<script>
	export default {
		data() {
			return {
				"title": "暂无计划"
			}
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
		height: 400rpx;
		width: 400rpx;
		margin: 100rpx auto 50rpx auto;
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
