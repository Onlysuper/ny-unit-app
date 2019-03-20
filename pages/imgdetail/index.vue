<template>
	<view class="ny-detail-page">
		<view class="ny-main">
			<view class="ny-title">一到这个季节就容易犯困</view>
			<view class="ny-imgbox">
				 <image src="../../static/logo.png"></image>
			</view>
			<view class="ny-content">
				一到这个季节就容易犯困一到这个季节就容易犯困一到这个季节就容易犯困一到这个季节就容易犯困一到这个季节就容易犯困
			</view>
		</view>
		<view class="ny-footer">
			<view>
				 <input class="uni-input" focus placeholder="自动获得焦点" />
			</view>
			<view class="ny-button-group">
				<view @click="showComments">评论</view>
				<view>收藏</view>
				<view>转发</view>
			</view>
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
			showComments(){
				uni.navigateTo({
					url: '/pages/detail/comment'
				});
			}
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
			 @include ny-padding-side();
			flex: 1;
			.ny-imgbox{
				flex:1;
				image{
					max-width: 100%;
				}
			}
		}
		.ny-footer{
			 @include ny-padding-side();
			flex: 0 0 100upx;
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
