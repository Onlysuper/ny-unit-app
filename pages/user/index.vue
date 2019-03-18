<template>
	<view class=" ny-user-page">
		<view class="ny-user-top">
			<view class="user-box">
				<view class="img-back"></view>
				<view class="user-context">
					<view class="name">亲宝宝</view>
					<view class="describe">快来完善一下个人信息吧</view>
				</view>
				<uni-icon color="#626466" type="arrowright" size="30"></uni-icon>
				<view class="bb-border-bottom"></view>
			</view>
			<view class="ny-grid-group">
				<view class="ny-grid-item">
					<view class="ny-num">4.9w</view>
					<view>获赞</view>
				</view>
				<view class="ny-grid-item">
					<view class="ny-num">100</view>
					<view>关注</view>
				</view>
				<view class="ny-grid-item">
					<view class="ny-num">999w</view>
					<view>粉丝</view>
				</view>
			</view>
		</view>
		<view class="ny-list-group">
			<uni-list-item class='ny-list' title="收藏"  show-extra-icon="true"  thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png" ></uni-list-item>
			<uni-list-item class='ny-list' title="设置" show-extra-icon="true"  thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item>
			<uni-list-item class='ny-list' title="关于" show-extra-icon="true"  thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item>
		</view>
	</view>
</template>

<script>
	import uniList from '@/components/uni-list/uni-list.vue'
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
	import uniIcon from "@/components/uni-icon/uni-icon.vue"
	export default {
		components: {uniList,uniListItem,uniIcon},
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
			
			.user-box{
				padding-left:30rpx;
				padding-right:30rpx;
				height: 160rpx;
				display: flex;
				flex-direction: row;
				align-items: center;
				position: relative;

				.img-back{
					flex: 0 0 120rpx;
					background:#eee;
					height: 120rpx;
					border-radius: 100%;
				}
				.user-context{
					padding-left: 30rpx;
					flex: 1;
					.name{
						font-size: 42rpx;
						color: $import-text-color;
					}
					.describe{
						font-size: 22rpx;
						color:$second-text-color;
					}
				}
			}
		}
		.ny-grid-group{
			padding-left:30rpx;
			padding-right:30rpx;
			display: flex;
			justify-content: space-between;
			align-items: center;
			height: 100rpx;
			.ny-grid-item{
				display: flex;
				flex-direction: row;
				justify-content: center;
				align-items: center;
				color: $second-text-color;
				font-size: 34rpx;
				.ny-num{
					padding-right: 10rpx;
				}
			}
		}
		.ny-list-group{
			padding-left: 30rpx;
			padding-right: 30rpx;
			.ny-list{
				color: $second-text-color
			}
		}
	}
</style>
