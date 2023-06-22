<template>
	<view class="content">
		<image class="logo" src="/static/home.png"></image>

		<view class="title">{{title}}</view>

		<view>
			<view class="wraper" @click="calculator">
				<view class="column" :style="{transform: `translateY(${-lineHeight*index4}rpx)`}">
					<view class="num" v-for="(item, index) in arr4" :key="index">{{ item }}</view>
				</view>
				<view class="column" :style="{transform: `translateY(${-lineHeight*index3}rpx)`}">
					<view class="num" v-for="(item, index) in arr3" :key="index">{{ item }}</view>
				</view>
			</view>

			<view class="wraper" @click="calculator">
				<view class="column" :style="{transform: `translateY(${-lineHeight*index2}rpx)`}">
					<view class="num" v-for="(item, index) in arr4" :key="index">{{ item }}</view>
				</view>
				<view class="column" :style="{transform: `translateY(${-lineHeight*index1}rpx)`}">
					<view class="num" v-for="(item, index) in arr3" :key="index">{{ item }}</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: "开始新的一天",
				timer: null,

				lineHeight: 250,
				arr1: [9, 8, 7, 6, 5, 4, 3, 2, 1, 0],
				index1: 9,
				arr2: [5, 4, 3, 2, 1, 0],
				index2: 5,
				arr3: [9, 8, 7, 6, 5, 4, 3, 2, 1, 0],
				index3: 9,
				arr4: [5, 4, 3, 2, 1, 0],
				index4: 2
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
			// 个人微信小程序无法获取用户手机号
			// // 获取用户手机号
			// getPhoneNumber(e) {

			// 	console.log(e.detail.errMsg) // 判断用户是否允许获取手机号
			// 	console.log(e.detail.iv) // 参数 iv
			// 	console.log(e.detail.encryptedData) // 参数encryptedData
			// 	if (e.detail.errMsg == "getPhoneNumber:ok") { // 用户允许或去手机号
			// 		uni.request({
			// 			url: "http://192.168.0.93:6042/login/miniProgramLogin",
			// 			method: "POST",
			// 			data: {
			// 				data: {
			// 					encryptedData: e.detail.encryptedData,
			// 					iv: e.detail.iv,
			// 					sessionKey: this.session_key,
			// 					openId: this.openId,
			// 				}
			// 			},
			// 			success: (res) => {
			// 				if (res.data.errorinfo == null) {
			// 					console.log(res.data) // 这个里面就有手机号了

			// 				}
			// 			}
			// 		})
			// 	}
			// },
			calculator() {
				if (this.timer == null) {
					this.start()
				} else {
					this.reset()
				}
			},
			start() {
				if (this.timer == null) {
					this.index1 = 0
					this.index2 = 0
					this.index3 = 0
					this.index4 = 3
					this.turnSecond(this.arr1.length)
				}
			},
			reset() {
				if (this.timer != null) {
					clearInterval(this.timer)
					this.timer = null
					this.index1 = 9
					this.index2 = 5
					this.index3 = 9
					this.index4 = 2
				}
			},
			turnSecond(length) {
				this.timer = setInterval(() => {
					if (this.index1 === length - 1) {
						this.turnOther(2, this.arr2.length)
						this.index1 = -1
					}
					this.index1++
				}, 1000)
			},
			turnOther(type, length) {
				if (this[`index${type}`] === length - 1) {
					console.log(type)
					let next = type + 1
					this.turnOther(next, this[`arr${next}`].length)
					this[`index${type}`] = -1
				}
				this[`index${type}`]++
			}
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

	.wraper {
		text-align: center;
		background-color: #ffffff;
		height: 250rpx;
		font-family: "Microsoft YaHei";
		font-size: 200rpx;
		color: #c9beff;
		font-weight: bolder;
		letter-spacing: 7rpx;
		margin-top: 7rpx;
		display: flex;
		justify-content: center;
		overflow: hidden
	}

	.column {
		transition: transform 300ms;
	}

	.num {
		height: 250rpx;
		font-size: 200rpx;
	}
</style>