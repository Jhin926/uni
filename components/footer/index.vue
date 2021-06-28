<template>
	<view class="footer">
		<view>预览</view>
		<view>任务</view>
		<view>我的</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				news: []
			};
		},
		onLoad: function() {},
		methods: {},
	}
</script>

<style scoped>
	.footer {
		display: flex;
		padding: 5px 0;
		border-top: 1px solid #eee;
		justify-content: space-around;
	}
</style>
