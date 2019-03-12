<template>
	<!-- <view class="uni-padding-wrap bb-banner-back">
		<view class="page-section swiper">
			<view class="page-section-spacing">
				<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
					<swiper-item>
						<view class="swiper-item uni-bg-red">
							<navigator url="/pages/baby/index">
							 <image src="../../static/logo.png"></image>
							</navigator>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item uni-bg-green">
							<navigator url="/pages/baby/index">
							 <image src="../../static/logo.png"></image>
							</navigator>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item uni-bg-blue">
							<navigator url="/pages/baby/index">
							 <image src="../../static/logo.png"></image>
							</navigator>
						</view>
					</swiper-item>
				</swiper>
			</view>
		</view>
	</view> -->
	<view class="ny-page-space ny-index-page">
		<view class="ny-list-container">
			<view class="ny-list-item">
				<view class="ny-img-outer">
					
				</view>
				<view class="ny-text-outer">
					<view class="ny-title">
						今天天气怎么样
					</view>
					<view class="ny-content">
						今天天气怎么样今天天气怎么样今天天气怎么样今天天气怎么样今天天气怎么样今天天气怎么样
					</view>
				</view>
				<view class="bb-border-bottom"></view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				background: ['color1', 'color2', 'color3'],
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500
			}
		},
		onLoad() {

		},
		methods: {
			changeIndicatorDots(e) {
				this.indicatorDots = !this.indicatorDots
			},
			changeAutoplay(e) {
				this.autoplay = !this.autoplay
			},
			intervalChange(e) {
				this.interval = e.target.value
			},
			durationChange(e) {
				this.duration = e.target.value
			}
		}
	}
</script>

<style lang="scss">
	 @import "../../style/common.scss";
	.ny-index-page{
		padding-left:  30rpx;
		padding-right:  30rpx;
		.ny-list-container{
			.ny-list-item{
				display: flex;
				flex-direction: row;
				align-items: center;
				padding: 30rpx 0;
				position: relative;
				.ny-img-outer{
					flex:0 0  100rpx;
					height: 100rpx;
					background:#eee;
				}
				.ny-text-outer{
					flex: 1;
					font-size: 32rpx;
					padding-left: 30rpx;
				}
			}
		}
	}
</style>
