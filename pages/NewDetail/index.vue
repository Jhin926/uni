<template>
	<view class="new-detail">
		<view class="title">
			<text>标题标题，标题标题，标题标题，标题标题，标题标题，标题标题，标题标题，标题标题，标题标题，标题标题，我是标题标题，</text>
		</view>
		<view class="author">
			
		</view>
		<view class="content">
			<text>内容内容，我是内容。内容内容，我是内容。内容内容，我是内容。内容内容，我是内容。内容内容，我是内容。内容内容，我是内容。内容内容，我是内容。内容内容，我是内容。内容内容，我是内容。内容内容，我是内容。内容内容，我是内容。
			内容内容，我是内容。内容内容，我是内容。内容内容，我是内容。内容内容，我是内容。</text>
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
		onLoad: function() {},
		methods: {
			openDetail() {
				uni.navigateTo({
					url: '../info/info?newsid='+newsid
				});
			}
		},
	}
</script>

<style scoped>
	.new-detail {
		padding: 8px 10px;
	}

	.title {
		font-size: 18px;
		margin-bottom: 8px;
	}
	
	.content {
		font-size: 14px;
	}
</style>
