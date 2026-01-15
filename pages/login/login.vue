<template>
	<view class="container">
		<!-- 登录标题 -->
		<view class="login-header">
			<view class="login-title">欢迎回来</view>
			<view class="login-subtitle">登录体验完整功能</view>
		</view>

		<!-- 登录表单 -->
		<view class="login-form">
			<view class="form-item">
				<view class="form-label">手机号</view>
				<input class="form-input" type="number" placeholder="请输入手机号" v-model="phone" />
			</view>

			<view class="form-item">
				<view class="form-label">验证码</view>
				<view class="verify-group">
					<input class="form-input" type="number" placeholder="请输入验证码" v-model="code" />
					<button class="verify-btn" @click="getVerifyCode">获取验证码</button>
				</view>
			</view>

			<button class="login-submit" @click="demoLogin">登录</button>
		</view>

		<!-- 演示提示 -->
		<view class="demo-tips">
			<view class="tips-title">🎮 演示版本登录</view>
			<view class="tips-content">
				• 输入任意手机号即可体验\n
				• 验证码请输入：123456\n
				• 真实版本将发送真实短信验证码\n
				• 支持微信一键登录等多种方式
			</view>
		</view>

		<!-- 其他登录方式 -->
		<view class="other-login">
			<view class="divider">
				<view class="line"></view>
				<view class="text">其他登录方式</view>
				<view class="line"></view>
			</view>

			<view class="login-methods">
				<button class="method-btn wechat" @click="demoWechatLogin">
					<view class="method-icon">💬</view>
					<view class="method-text">微信登录</view>
				</button>
				<button class="method-btn qq" @click="demoQQLogin">
					<view class="method-icon">🐧</view>
					<view class="method-text">QQ登录</view>
				</button>
			</view>
		</view>

		<!-- 快速体验 -->
		<view class="quick-experience">
			<button class="quick-btn" @click="quickDemo">快速体验（无需登录）</button>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			phone: '',
			code: ''
		}
	},
	methods: {
		getVerifyCode() {
			if (!this.phone) {
				uni.showToast({
					title: '请输入手机号',
					icon: 'none'
				})
				return
			}
			uni.showToast({
				title: '验证码已发送：123456',
				icon: 'none'
			})
			this.code = '123456'
		},
		demoLogin() {
			if (!this.phone || !this.code) {
				uni.showToast({
					title: '请填写完整信息',
					icon: 'none'
				})
				return
			}
			if (this.code !== '123456') {
				uni.showToast({
					title: '验证码错误，请输入123456',
					icon: 'none'
				})
				return
			}
			uni.showToast({
				title: '登录成功！',
				icon: 'success'
			})
			setTimeout(() => {
				uni.switchTab({
					url: '/pages/index/index'
				})
			}, 1500)
		},
		demoWechatLogin() {
			uni.showToast({
				title: '演示版本 - 微信登录',
				icon: 'none'
			})
		},
		demoQQLogin() {
			uni.showToast({
				title: '演示版本 - QQ登录',
				icon: 'none'
			})
		},
		quickDemo() {
			uni.showToast({
				title: '进入快速体验模式',
				icon: 'none'
			})
			setTimeout(() => {
				uni.switchTab({
					url: '/pages/index/index'
				})
			}, 1000)
		}
	}
}
</script>

<style scoped>
.container {
	padding: 20px;
	background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
	min-height: 100vh;
	display: flex;
	flex-direction: column;
}

.login-header {
	text-align: center;
	margin-bottom: 40px;
	color: white;
}

.login-title {
	font-size: 28px;
	font-weight: bold;
	margin-bottom: 10px;
}

.login-subtitle {
	font-size: 16px;
	opacity: 0.8;
}

.login-form {
	background: white;
	border-radius: 15px;
	padding: 30px 20px;
	margin-bottom: 20px;
	box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.form-item {
	margin-bottom: 20px;
}

.form-label {
	font-size: 14px;
	color: #333;
	margin-bottom: 8px;
	font-weight: 500;
}

.form-input {
	width: 100%;
	height: 45px;
	border: 1px solid #e0e0e0;
	border-radius: 8px;
	padding: 0 15px;
	font-size: 14px;
	transition: border-color 0.3s ease;
}

.form-input:focus {
	border-color: #667eea;
	outline: none;
}

.verify-group {
	display: flex;
	gap: 10px;
}

.verify-group .form-input {
	flex: 1;
}

.verify-btn {
	background: #667eea;
	color: white;
	border: none;
	border-radius: 8px;
	padding: 0 15px;
	font-size: 12px;
	white-space: nowrap;
}

.login-submit {
	width: 100%;
	height: 50px;
	background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
	color: white;
	border: none;
	border-radius: 25px;
	font-size: 16px;
	font-weight: bold;
	margin-top: 10px;
	box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
}

.demo-tips {
	background: rgba(255, 255, 255, 0.95);
	border-radius: 10px;
	padding: 15px;
	margin-bottom: 20px;
}

.tips-title {
	font-size: 14px;
	font-weight: bold;
	color: #856404;
	margin-bottom: 8px;
}

.tips-content {
	font-size: 12px;
	color: #856404;
	line-height: 1.5;
}

.other-login {
	margin-bottom: 20px;
}

.divider {
	display: flex;
	align-items: center;
	margin-bottom: 20px;
}

.line {
	flex: 1;
	height: 1px;
	background: rgba(255, 255, 255, 0.3);
}

.text {
	color: white;
	font-size: 12px;
	margin: 0 15px;
	opacity: 0.8;
}

.login-methods {
	display: flex;
	justify-content: center;
	gap: 30px;
}

.method-btn {
	background: rgba(255, 255, 255, 0.2);
	border: 1px solid rgba(255, 255, 255, 0.3);
	border-radius: 50%;
	width: 60px;
	height: 60px;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	color: white;
}

.method-icon {
	font-size: 20px;
	margin-bottom: 2px;
}

.method-text {
	font-size: 10px;
}

.quick-experience {
	text-align: center;
}

.quick-btn {
	background: transparent;
	color: white;
	border: 1px solid rgba(255, 255, 255, 0.5);
	border-radius: 20px;
	padding: 10px 20px;
	font-size: 12px;
	opacity: 0.8;
}
</style>