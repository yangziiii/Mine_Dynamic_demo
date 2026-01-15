<template>
	<div id="app">
		<router-view />
	</div>
</template>

<script>
export default {
  onLaunch: function() {
    console.log('App Launch - 学习计划助手演示版本')
  },
  onShow: function() {
    console.log('App Show')
  },
  onHide: function() {
    console.log('App Hide')
  }
}
</script>

<style>
/* 每个页面公共css */
@import './static/styles/common.css';

/* 全局样式 */
page {
	background-color: #f5f5f5;
}

/* 重置样式 */
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}

/* 按钮样式重置 */
button {
	margin: 0;
	padding: 0;
	outline: none;
	border: none;
	background: none;
}

button:after {
	border: none;
}

/* 文本样式 */
.text-center {
	text-align: center;
}

.text-primary {
	color: #667eea;
}

.text-success {
	color: #4CAF50;
}

.text-warning {
	color: #FF9800;
}

.text-danger {
	color: #f44336;
}

/* 布局样式 */
.flex {
	display: flex;
}

.flex-center {
	display: flex;
	align-items: center;
	justify-content: center;
}

.flex-between {
	display: flex;
	align-items: center;
	justify-content: space-between;
}

.flex-column {
	display: flex;
	flex-direction: column;
}

.flex-1 {
	flex: 1;
}

/* 间距样式 */
.mt-10 { margin-top: 10px; }
.mt-20 { margin-top: 20px; }
.mb-10 { margin-bottom: 10px; }
.mb-20 { margin-bottom: 20px; }
.ml-10 { margin-left: 10px; }
.mr-10 { margin-right: 10px; }
.p-10 { padding: 10px; }
.p-20 { padding: 20px; }

/* 圆角样式 */
.rounded {
	border-radius: 8px;
}

.rounded-lg {
	border-radius: 15px;
}

/* 阴影样式 */
.shadow {
	box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.shadow-lg {
	box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}
</style>