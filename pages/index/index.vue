<template>
	<view class="container">
		<!-- 顶部导航 -->
		<view class="nav-bar">
			<view class="nav-title">学习计划助手</view>
			<view class="nav-subtitle">智能制定个性化学习计划</view>
		</view>

		<!-- 功能卡片 -->
		<view class="feature-cards">
			<view class="card" @click="goToSchedule">
				<view class="card-icon">📚</view>
				<view class="card-title">制定计划</view>
				<view class="card-desc">AI智能推荐学习路径</view>
			</view>

			<view class="card" @click="showDemo">
				<view class="card-icon">📊</view>
				<view class="card-title">进度追踪</view>
				<view class="card-desc">可视化学习进度</view>
			</view>

			<view class="card" @click="showDemo">
				<view class="card-icon">🎯</view>
				<view class="card-title">目标管理</view>
				<view class="card-desc">设定并达成学习目标</view>
			</view>
		</view>

		<!-- 演示说明 -->
		<view class="demo-notice">
			<view class="notice-title">🎮 演示版本说明</view>
			<view class="notice-content">
				• 此为前端UI演示版本\n
				• 所有数据均为模拟数据\n
				• 真实功能需要后端API支持\n
				• 点击下方按钮体验完整流程
			</view>
		</view>

		<!-- 体验按钮 -->
		<view class="demo-buttons">
			<button class="demo-btn primary" @click="goToSchedule">体验完整流程</button>
			<button class="demo-btn secondary" @click="showLoginDemo">登录演示</button>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {}
	},
	methods: {
		goToSchedule() {
			uni.navigateTo({
				url: '/pages/schedule/schedule'
			})
		},
		showLoginDemo() {
			uni.navigateTo({
				url: '/pages/login/login'
			})
		},
		showDemo() {
			uni.showToast({
				title: '演示功能',
				icon: 'none'
			})
		}
	}
}
</script>

<style scoped>
.container {
	padding: 20px;
	background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
	min-height: 100vh;
}

.nav-bar {
	text-align: center;
	margin-bottom: 40px;
}

.nav-title {
	font-size: 32px;
	color: white;
	font-weight: bold;
	margin-bottom: 10px;
}

.nav-subtitle {
	font-size: 16px;
	color: rgba(255, 255, 255, 0.8);
}

.feature-cards {
	display: flex;
	flex-direction: column;
	gap: 20px;
	margin-bottom: 40px;
}

.card {
	background: white;
	border-radius: 15px;
	padding: 25px;
	text-align: center;
	box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
	transition: transform 0.3s ease;
}

.card:active {
	transform: scale(0.98);
}

.card-icon {
	font-size: 40px;
	margin-bottom: 15px;
}

.card-title {
	font-size: 20px;
	font-weight: bold;
	color: #333;
	margin-bottom: 8px;
}

.card-desc {
	font-size: 14px;
	color: #666;
}

.demo-notice {
	background: rgba(255, 255, 255, 0.95);
	border-radius: 10px;
	padding: 20px;
	margin-bottom: 30px;
}

.notice-title {
	font-size: 18px;
	font-weight: bold;
	color: #333;
	margin-bottom: 10px;
}

.notice-content {
	font-size: 14px;
	color: #666;
	line-height: 1.6;
}

.demo-buttons {
	display: flex;
	flex-direction: column;
	gap: 15px;
}

.demo-btn {
	padding: 15px 30px;
	border: none;
	border-radius: 25px;
	font-size: 16px;
	font-weight: bold;
	transition: all 0.3s ease;
}

.demo-btn.primary {
	background: #4CAF50;
	color: white;
}

.demo-btn.secondary {
	background: #2196F3;
	color: white;
}

.demo-btn:active {
	opacity: 0.8;
	transform: scale(0.98);
}
</style>