<script>
	export default {
		onLaunch: function() {
			console.log("App onLaunch")
			// this.login();
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		},
		methods: {
			// login() {
			// 	// wx.login()获取code
			// 	uni.login({
			// 		provider: 'weixin',
			// 		success: (res) => {
			// 			console.log("code: " + res.code);
			// 			 uni.request({  
			// 				url: 'https://api.weixin.qq.com/sns/jscode2session',  
			// 					method:'GET',  
			// 					data: {  
			// 						appid: 'wxc7c244ea5ebdb2a9',                         //你的小程序的APPID  
			// 						secret: '3b017ab04f3f013807a50d758ddda259',                 //你的小程序的secret,  
			// 						js_code:res.code,                                 //wx.login 登录成功后的code  
			// 						grant_type: 'authorization_code',
			// 					},  
			// 					success: (cts) => {  
			// 						// 换取成功后 暂存这些数据 留作后续操作  
			// 						this.openId=cts.data.openid               //openid 用户唯一标识  
			// 						this.unionid=cts.data.unionid             //unionid 开放平台唯一标识   当公众号和小程序同时登录过才会有
			// 						this.session_key=cts.data.session_key     //session_key  会话密钥  
			// 						console.log(cts)
			// 						console.log("sessiong_key: ", this.session_key)
			// 						console.log("openId: ",this.openId)
			// 					}  
			// 				}); 

			// 		}
			// 	})
			// }
		}

	}
</script>

<style>
	/*每个页面公共css */
</style>