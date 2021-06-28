<template>
	<view class="container">
		<view class="header">
			<search-header></search-header>
			<scroll-view scroll-x="true" class="scroll-view_H">
				<view class="scroll-view-item" :class="{'active': checkId === item.value}" v-for="item in navList"
					@tap="openinfo(item)">
					{{item.title}}
				</view>
			</scroll-view>
		</view>
		<view class="content">
			<scroll-view class="news-list">
				<view v-for="item in newsList">
					<component :is="componentMap[item.type]" :data="item"></component>
				</view>
			</scroll-view>
		</view>
	</view>
</template>

<script>
	import SearchHeader from '@/components/header/index.vue'
	import TopNew from '@/components/TopNew/index.vue'
	export default {
		data() {
			return {
				componentMap: {
					'0': 'TopNew',
					'1': 'TopNew',
					'2': 'TopNew',
					'3': 'TopNew',
				},
				newsList: [{
						title: '上海道路实况',
						author: '北青网',
						forward: '20',
						comment: '50',
						time: '5天前',
						id: '0',
						type: '0'
					},
					{
						title: '撕葱土味情话',
						author: '北青网',
						forward: '20',
						comment: '50',
						time: '5天前',
						imgSrc: 'https://nimg.ws.126.net/?url=http://bjnewsrec-cv.ws.126.net/three1651dd97fafp00qv8j6r003ic000i200cdm.jpg&thumbnail=140y88&quality=80&type=jpg',
						id: '1',
						type: '1'
					},
					{
						title: '上海道路实况',
						author: '北青网',
						forward: '20',
						comment: '50',
						time: '5天前',
						videoSrc: 'http://dop.deppon.com/static/media/newcomerGuide.8ac5864.mp4',
						id: '2',
						type: '2'
					},
					{
						title: '上海道路实况',
						author: '北青网',
						forward: '20',
						comment: '50',
						time: '5天前',
						id: '3',
						type: '3'
					},
				],
				checkId: '1',
				navList: [{
						title: '关注',
						value: '0'
					},
					{
						title: '推荐',
						value: '1'
					},
					{
						title: '热榜',
						value: '2'
					},
					{
						title: '职场',
						value: '3'
					},
					{
						title: '励志',
						value: '4'
					},
					{
						title: '情感',
						value: '5'
					},
					{
						title: '家庭',
						value: '6'
					},
				]
			};
		},
		components: {
			SearchHeader,
			TopNew
		},
		onLoad: function() {
			uni.showLoading({
				title: "加载中...."
			})
			uni.request({
				url: 'https://unidemo.dcloud.net.cn/api/news',
				method: 'GET',
				data: {},
				success: res => {
					this.news = res.data;
					uni.hideLoading();
				},
				fail: () => {},
				complete: () => {}
			});
		},
		methods: {
			openinfo(item) {
				this.checkId = item.value;
			}
		},
	}
</script>

<style>
	page {
		width: 100%;
		height: 100%;
	}
	.container {
		height: 100%;
		margin: 0 10px;
		display: flex;
		flex-direction: column;
	}

	.header {
		height: 78px;
	}

	.scroll-view_H {
		white-space: nowrap;
		width: 100%;
		border-bottom: 1px solid #bbb;
	}

	.scroll-view-item {
		font-size: 14px;
		display: inline-block;
		margin: 0 6px;
		padding: 8px 0;
	}

	.scroll-view-item.active {
		border-bottom: 1px solid #cf545a;
		color: #cf545a;
	}


	.content {
		flex: 1;
		position: relative;
		overflow-y: auto;
	}
	.news-list {
	}
	.footer {
	}
</style>
