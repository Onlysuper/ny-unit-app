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
		padding: 0 30upx;
		.user-box{
			height: 120upx;
			display: flex;
			flex-direction: row;
			align-items: center;
			position: relative;
			.img-back{
				flex: 0 0 100upx;
				background:#eee;
				height: 100upx;
				border-radius: 100%;
			}
			.user-context{
				padding-left: 10upx;
				flex: 1;
				.name{
					font-size: 32upx;
				}
				.describe{
					font-size: 22upx;
				}
			}
		}
	}
</style>
