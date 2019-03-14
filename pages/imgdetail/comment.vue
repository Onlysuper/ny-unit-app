<template>
	<view class="ny-detail-page">
		评论列表
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
	.ny-detail-page{
		position: absolute;
		right: 0;
		left: 0;
		bottom: 0;
		top: 0;
		display: flex;
		flex-direction: column;
		.ny-main{
			flex: 1;
			.ny-imgbox{
				flex:1;
				image{
					max-width: 100%;
				}
			}
		}
		.ny-footer{
			flex: 0 0 100rpx;
			background:#eee;
			display: flex;
			flex-direction: row;
			align-items: center;
			justify-content: flex-start;
			.ny-button-group{
				display: flex;
				flex-direction: row;
			}
		}
	}
</style>
