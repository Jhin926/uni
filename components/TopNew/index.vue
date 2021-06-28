<template>
	<view class="top-new" @tap="openDetail">
		<view class="title">
			<text>{{data.title}}</text>
		</view>
		<view v-if="data.type === '1'">
			<image class="new-img" :src="data.imgSrc"></image>
		</view>
		<view v-if="data.type === '2'">
			<video class="new-video" :src="data.imgSrc"></video>
		</view>
		<view>
			<text class="footer">北青网 转发 20 评论 50 5天前</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				news: []
			};
		},
		props: ['data'],
		onLoad: function() {},
		methods: {
			openDetail() {
				console.log(323)
				uni.navigateTo({
					url: '../NewDetail/index'
				});
			}
		},
	}
</script>

<style scoped>
	.top-new {
		padding: 8px 5px;
	}

	.title {
		font-size: 16px;
		margin-bottom: 8px;
	}
	
	.new-img {
		width: 200px;
		height: 100px;
		background-color: #eee;
	}
	
	.new-video {
		width: 100%;
		height: 200px;
		background-color: #eee;
	}

	.footer {
		font-size: 13px;
	}
</style>
