<template>
	<view class=" ny-user-page">
		<view class="ny-user-top">
			<view class="user-box">
				<view class="img-back"></view>
				<view class="user-context">
					<view class="name">亲宝宝</view>
					<view class="describe">快来完善一下个人信息吧</view>
				</view>
				<view class="bb-border-bottom"></view>
			</view>
			<view class="ny-grid-group">
				<view class="ny-grid-item">4.9w获赞</view>
				<view class="ny-grid-item">100关注</view>
				<view class="ny-grid-item">100w粉丝</view>
			</view>
		</view>
		<uni-list-item title="收藏" thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item></uni-list-item>
		<uni-list-item title="设置" thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item></uni-list-item>
		<uni-list-item title="关于" thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item></uni-list-item>
	</view>
</template>

<script>
	import uniList from '@/components/uni-list/uni-list.vue'
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
	export default {
		components: {uniList,uniListItem},
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss">
	 @import "../../style/common.scss";
	.ny-user-page{
		.ny-user-top{
			padding-left:30rpx;
			padding-right:30rpx;
			.user-box{
				height: 120rpx;
				display: flex;
				flex-direction: row;
				align-items: center;
				position: relative;
				.img-back{
					flex: 0 0 100rpx;
					background:#eee;
					height: 100rpx;
					border-radius: 100%;
				}
				.user-context{
					padding-left: 10rpx;
					flex: 1;
					.name{
						font-size: 32rpx;
					}
					.describe{
						font-size: 22rpx;
					}
				}
			}
		}
		.ny-grid-group{
			display: flex;
			justify-content: space-between;
			align-items: center;
			height: 100rpx;
			.ny-grid-item{
				font-size: 30rpx;
			}
		}
	}
</style>
