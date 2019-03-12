<template>
	<view class="ny-page-space user-page">
		<view class="user-box">
			<view class="img-back"></view>
			<view class="user-context">
				<view class="name">亲宝宝</view>
				<view class="describe">快来完善一下个人信息吧</view>
			</view>
			<view class="bb-border-bottom"></view>
		</view>
	</view>
</template>

<script>
	export default {
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
	.user-page{
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
</style>
