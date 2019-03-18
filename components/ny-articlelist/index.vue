<template>
<!-- 文章内容区 -->
	<view class="grace-news-list" style="width:94%; padding:5px 3%;">
		<block v-for="(item, index) in list" :key="index">
			<!-- 一张图 -->
			<navigator url="/pages/article/article-info/article-info" v-if="item.imgs.length < 3" open-type="navigate">
				<view class="grace-news-list-img-news">
					<view class="grace-news-list-title-main">{{item.title}}</view>
					<view class="grace-news-list-img-big"><image :src="item.imgs[0]" mode="widthFix"></image></view>
				</view>
			</navigator>
			<!-- 三张图 -->
			<navigator url="/pages/article/article-info/article-info" v-if="item.imgs.length >= 3">
				<view class="grace-news-list-img-news">
					<view class="grace-news-list-title-main">{{item.title}}</view>
					<view class="grace-news-list-imgs">
						<image :src="item.imgs[0]" mode="widthFix"></image>
						<image :src="item.imgs[1]" mode="widthFix"></image>
						<image :src="item.imgs[2]" mode="widthFix"></image>
					</view>
				</view>
			</navigator>
		</block>
	</view>
</template>
<style lang="scss">
	@import "../../style/article.scss";
</style>
<script>
	export default{
		props:{
			list:{
				type:Array,
				default:[]
			}
		}
	}
</script>