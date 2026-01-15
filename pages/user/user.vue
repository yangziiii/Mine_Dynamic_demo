<template>
	<view class="container">
		<!-- 用户信息卡片 -->
		<view class="user-card">
			<view class="avatar-section">
				<view class="avatar">👤</view>
				<view class="user-info">
					<view class="username">演示用户</view>
					<view class="user-level">初级学习者</view>
				</view>
			</view>
			<view class="stats-section">
				<view class="stat-item">
					<view class="stat-number">12</view>
					<view class="stat-label">已完成</view>
				</view>
				<view class="stat-item">
					<view class="stat-number">4</view>
					<view class="stat-label">进行中</view>
				</view>
				<view class="stat-item">
					<view class="stat-number">156</view>
					<view class="stat-label">学习时长</view>
				</view>
			</view>
		</view>

		<!-- 功能列表 -->
		<view class="function-list">
			<view class="function-item" @click="showDemoFeature('学习统计')">
				<view class="function-icon">📊</view>
				<view class="function-content">
					<view class="function-title">学习统计</view>
					<view class="function-desc">查看学习进度和成果</view>
				</view>
				<view class="arrow">›</view>
			</view>

			<view class="function-item" @click="showDemoFeature('成就系统')">
				<view class="function-icon">🏆</view>
				<view class="function-content">
					<view class="function-title">成就系统</view>
					<view class="function-desc">解锁学习成就徽章</view>
				</view>
				<view class="arrow">›</view>
			</view>

			<view class="function-item" @click="showDemoFeature('设置')">
				<view class="function-icon">⚙️</view>
				<view class="function-content">
					<view class="function-title">设置</view>
					<view class="function-desc">个性化配置</view>
				</view>
				<view class="arrow">›</view>
			</view>

			<view class="function-item" @click="showDemoFeature('帮助反馈')">
				<view class="function-icon">💬</view>
				<view class="function-content">
					<view class="function-title">帮助反馈</view>
					<view class="function-desc">获取帮助和提交反馈</view>
				</view>
				<view class="arrow">›</view>
			</view>
		</view>

		<!-- 演示说明 -->
		<view class="demo-notice">
			<view class="notice-title">🔒 演示版本说明</view>
			<view class="notice-content">
				当前为演示版本，仅展示UI界面和基础交互功能。真实版本包含完整的学习管理系统、AI智能推荐、进度追踪等核心功能。
			</view>
		</view>

		<!-- 登录按钮 -->
		<view class="login-section">
			<button class="login-btn" @click="showLoginDemo">切换账户</button>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {}
	},
	methods: {
		showDemoFeature(featureName) {
			uni.showToast({
				title: `演示版本 - ${featureName}`,
				icon: 'none',
				duration: 2000
			})
		},
		showLoginDemo() {
			uni.navigateTo({
				url: '/pages/login/login'
			})
		}
	}
}
</script>

<style scoped>
.container {
	padding: 20px;
	background: #f5f5f5;
	min-height: 100vh;
}

.user-card {
	background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
	border-radius: 15px;
	padding: 25px;
	margin-bottom: 20px;
	color: white;
	box-shadow: 0 10px 30px rgba(102, 126, 234, 0.3);
}

.avatar-section {
	display: flex;
	align-items: center;
	margin-bottom: 20px;
}

.avatar {
	width: 60px;
	height: 60px;
	background: rgba(255, 255, 255, 0.2);
	border-radius: 50%;
	display: flex;
	align-items: center;
	justify-content: center;
	font-size: 24px;
	margin-right: 15px;
}

.user-info {
	flex: 1;
}

.username {
	font-size: 20px;
	font-weight: bold;
	margin-bottom: 5px;
}

.user-level {
	font-size: 14px;
	opacity: 0.8;
}

.stats-section {
	display: flex;
	justify-content: space-around;
	padding-top: 15px;
	border-top: 1px solid rgba(255, 255, 255, 0.2);
}

.stat-item {
	text-align: center;
}

.stat-number {
	font-size: 24px;
	font-weight: bold;
	margin-bottom: 5px;
}

.stat-label {
	font-size: 12px;
	opacity: 0.8;
}

.function-list {
	background: white;
	border-radius: 15px;
	overflow: hidden;
	margin-bottom: 20px;
	box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.function-item {
	display: flex;
	align-items: center;
	padding: 15px 20px;
	border-bottom: 1px solid #f5f5f5;
	transition: background 0.3s ease;
}

.function-item:last-child {
	border-bottom: none;
}

.function-item:active {
	background: #f5f5f5;
}

.function-icon {
	font-size: 24px;
	margin-right: 15px;
	width: 30px;
	text-align: center;
}

.function-content {
	flex: 1;
}

.function-title {
	font-size: 16px;
	font-weight: 500;
	color: #333;
	margin-bottom: 3px;
}

.function-desc {
	font-size: 13px;
	color: #999;
}

.arrow {
	font-size: 20px;
	color: #ccc;
}

.demo-notice {
	background: #fff3cd;
	border: 1px solid #ffeaa7;
	border-radius: 10px;
	padding: 15px;
	margin-bottom: 20px;
}

.notice-title {
	font-size: 16px;
	font-weight: bold;
	color: #856404;
	margin-bottom: 8px;
}

.notice-content {
	font-size: 13px;
	color: #856404;
	line-height: 1.5;
}

.login-section {
	text-align: center;
}

.login-btn {
	background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
	color: white;
	border: none;
	border-radius: 25px;
	padding: 12px 30px;
	font-size: 14px;
	font-weight: bold;
	box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
}
</style>