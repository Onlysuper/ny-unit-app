<template>
	<view>
		<!-- 标题 -->
		<view :class="['grace-article-title', graceSkeleton == 'ing' ? 'grace-skeleton' : '']">{{article.title}}</view>
		<!-- 作者信息 -->
		<view class="grace-article-author-line">
			<view :class="['grace-article-author', graceSkeleton == 'ing' ? 'grace-skeleton' : '']">
				<image :src="article.authorFcae" mode="widthFix"></image>
				<view class="author-name">{{article.authorName}}</view>
			</view>
			<view class="btn"> + 关注 </view>
		</view>
		<!-- 其他基本信息 -->
		<view :class="['grace-article-info-line', graceSkeleton == 'ing' ? 'grace-skeleton' : '']">
			<view>{{article.viewNumber}}</view>
			<view>{{article.date}}</view>
		</view>
		<!-- 文章内容 -->
		<view class="grace-article-contents">
			<block v-for="(item, index) in article.contents" :key="index">
			<view :class="['img-item', graceSkeleton == 'ing' ? 'grace-skeleton' : '']" v-if="item.type == 'img'">
				<image :src="item.content" mode="widthFix"></image>
			</view>
			<view :class="['text-item', graceSkeleton == 'ing' ? 'grace-skeleton' : '']" v-if="item.type == 'text'">{{item.content}}</view>
			</block>
		</view>
	</view>
</template>
<script>
var _self;
export default {
	data() {
		return {
			graceSkeleton : 'ing',
			article : {
				contents : []
			}
		}
	},
	onLoad() {
		_self = this;
		// 加载文章详情
		uni.showLoading({});
		uni.request({
			url: 'https://www.easy-mock.com/mock/5c8ef1f56336eb1e219105de/ny/article-detail',
			method: 'GET',
			data: {},
			success: res => {
				// 此处先规划骨架
				var art = {contents : []};
				for(var i = 0; i < res.data.data.contents.length; i++){
					art.contents.push({'type': res.data.data.contents[i].type});
				}
				_self.article =  art;
				
				// 骨架屏规划后延长 500 毫秒进行数据替换
				setTimeout(function(){
					_self.article = res.data.data;
					_self.graceSkeleton = 'end';
					uni.setNavigationBarTitle({title : _self.article.title});
				}, 500);
			},
			fail: () => {},
			complete: () => {
				uni.hideLoading();
			}
		});
	},
	methods: {

	}
}
</script>
<style>
		  @import "../../../style/article.scss";
</style>