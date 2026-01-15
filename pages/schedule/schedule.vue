<template>
	<view class="container">
		<!-- 页面标题 -->
		<view class="page-header">
			<view class="header-title">📚 学习计划</view>
			<view class="header-subtitle">智能制定个性化学习路径</view>
		</view>

		<!-- 模拟学习计划列表 -->
		<view class="plan-list">
			<view class="plan-item" v-for="(plan, index) in demoPlans" :key="index">
				<view class="plan-header">
					<view class="plan-title">{{ plan.title }}</view>
					<view class="plan-progress">{{ plan.progress }}%</view>
				</view>
				<view class="plan-content">
					<view class="plan-desc">{{ plan.description }}</view>
					<view class="progress-bar">
						<view class="progress-fill" :style="{width: plan.progress + '%'}"></view>
					</view>
				</view>
				<view class="plan-footer">
					<view class="plan-time">⏰ {{ plan.duration }}</view>
					<view class="plan-status" :class="plan.statusClass">{{ plan.status }}</view>
				</view>
			</view>
		</view>

		<!-- 创建新计划按钮 -->
		<view class="create-section">
			<button class="create-btn" @click="createDemoPlan">
				<view class="btn-icon">➕</view>
				<view class="btn-text">创建新的学习计划</view>
			</button>
		</view>

		<!-- 演示说明 -->
		<view class="demo-info">
			<view class="info-title">💡 演示说明</view>
			<view class="info-content">
				• 以上为模拟学习计划数据\n
				• 真实版本将连接AI算法生成个性化计划\n
				• 支持智能时间分配和进度追踪\n
				• 提供详细的学习报告和分析
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			demoPlans: [
				{
					title: "JavaScript 进阶学习",
					description: "从基础到高级，系统学习JavaScript核心概念",
					progress: 75,
					duration: "4周",
					status: "进行中",
					statusClass: "status-progress"
				},
				{
					title: "Vue.js 框架掌握",
					description: "深入学习Vue.js框架，包含组件开发和状态管理",
					progress: 45,
					duration: "6周",
					status: "进行中",
					statusClass: "status-progress"
				},
				{
					title: "算法与数据结构",
					description: "掌握常用算法和数据结构，提升编程思维",
					progress: 100,
					duration: "8周",
					status: "已完成",
					statusClass: "status-completed"
				},
				{
					title: "前端工程化实践",
					description: "学习Webpack、Vite等构建工具，掌握现代前端开发流程",
					progress: 20,
					duration: "3周",
					status: "待开始",
					statusClass: "status-pending"
				}
			]
		}
	},
	methods: {
		createDemoPlan() {
			uni.showToast({
				title: '演示版本 - 无法创建真实计划',
				icon: 'none',
				duration: 2000
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

.page-header {
	text-align: center;
	margin-bottom: 30px;
	padding: 20px;
	background: white;
	border-radius: 15px;
	box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.header-title {
	font-size: 24px;
	font-weight: bold;
	color: #333;
	margin-bottom: 5px;
}

.header-subtitle {
	font-size: 14px;
	color: #666;
}

.plan-list {
	margin-bottom: 20px;
}

.plan-item {
	background: white;
	border-radius: 12px;
	padding: 20px;
	margin-bottom: 15px;
	box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.plan-header {
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-bottom: 10px;
}

.plan-title {
	font-size: 18px;
	font-weight: bold;
	color: #333;
}

.plan-progress {
	font-size: 16px;
	font-weight: bold;
	color: #4CAF50;
}

.plan-content {
	margin-bottom: 15px;
}

.plan-desc {
	font-size: 14px;
	color: #666;
	margin-bottom: 10px;
}

.progress-bar {
	height: 6px;
	background: #e0e0e0;
	border-radius: 3px;
	overflow: hidden;
}

.progress-fill {
	height: 100%;
	background: linear-gradient(90deg, #4CAF50, #8BC34A);
	border-radius: 3px;
	transition: width 0.3s ease;
}

.plan-footer {
	display: flex;
	justify-content: space-between;
	align-items: center;
}

.plan-time {
	font-size: 12px;
	color: #999;
}

.plan-status {
	font-size: 12px;
	padding: 4px 8px;
	border-radius: 12px;
	font-weight: bold;
}

.status-progress {
	background: #E3F2FD;
	color: #2196F3;
}

.status-completed {
	background: #E8F5E8;
	color: #4CAF50;
}

.status-pending {
	background: #FFF3E0;
	color: #FF9800;
}

.create-section {
	text-align: center;
	margin: 30px 0;
}

.create-btn {
	background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
	color: white;
	border: none;
	border-radius: 25px;
	padding: 15px 30px;
	font-size: 16px;
	font-weight: bold;
	display: flex;
	align-items: center;
	justify-content: center;
	gap: 10px;
	box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
}

.btn-icon {
	font-size: 20px;
}

.demo-info {
	background: white;
	border-radius: 12px;
	padding: 20px;
	box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.info-title {
	font-size: 16px;
	font-weight: bold;
	color: #333;
	margin-bottom: 10px;
}

.info-content {
	font-size: 13px;
	color: #666;
	line-height: 1.6;
}
</style>