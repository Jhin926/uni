<template>
	<view class="input-con">
		<input class="search-input" type="text" placeholder="搜想看的故事" />
	</view>
</template>

<script>
	export default {
		data() {
			return {
				news : []
			};
		},
		onLoad:function(){
		},
		methods: {
		},
	}
</script>

<style scoped>
	.input-con {
		display: flex;
		padding: 5px;
		background-color: #d4d4d4;
	}
	.search-input {
		width: 80%;
		height: 30px;
		padding: 0 5px;
		font-size: 14px;
		border-radius: 5px;
		background-color: white;
	}
</style>
