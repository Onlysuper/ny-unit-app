<template>
	<view class="ny-page-space user-page">
		这里
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
		padding: 0 30rpx;
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
