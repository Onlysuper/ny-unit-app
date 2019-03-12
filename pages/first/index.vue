<template>
	<view class="ny-page-space first-page">
		<view>
			这里
		</view>
		<button @click="chooseImgHandle">
			选择图片
		</button>
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
			chooseImgHandle(){
				uni.chooseImage({
					count: 6, //默认9
					sizeType: ['original', 'compressed'], //可以指定是原图还是压缩图，默认二者都有
					sourceType: ['album'], //从相册选择
					success: function (res) {
						  // 预览图片
						uni.previewImage({
							urls: res.tempFilePaths
						});
					}
				});
			}
		}
	}
</script>

<style lang="scss">
	@import "../../style/common.scss";
	.first-page{
		
	}
</style>
