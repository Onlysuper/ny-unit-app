<template>
	<view class="ny-imgtext-page">
		<view class="ny-main">
			
			<view class="ny-content">
				 <textarea placeholder="说点什么吧" @blur="bindTextAreaBlur" auto-height />
			</view>
			<view class="ny-picture">
				<ny-upimg ref="upimg" url="https://xxx" :count="6" :autoup="false" @onUpImg="upImgData" />
			</view>
		</view>
		<view class="ny-list-group">
			<uni-tag  class='ny-list' text="标签" type="" :circle="true"></uni-tag>
			<uni-list-item class='ny-list' title="谁可以看" show-extra-icon="true"  thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item>
			<uni-list-item class='ny-list' title="所在位置" show-extra-icon="true"  thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item>
			<uni-list-item class='ny-list' title="记录时间" show-extra-icon="true"  thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item>
		</view>
	</view>
</template>

<script>
	import uniTag from "@/components/uni-tag/uni-tag.vue"
	import nyUpimg from '@/components/ny-upimg/ny-upimg.vue'
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		components: {
			nyUpimg,
			uniListItem,
			uniTag
		},
		onLoad() {
			// chooseImage
		
		},
		//获取上传图片的所有信息,为数组
		upImgData(e){
			console.log('来了,伙计',e)
		},
		methods: {
			bindTextAreaBlur: function (e) {
				console.log(e.detail.value);
				uni.chooseImage({
					sourceType: ['album', 'camera'],
					success(res) {
						console.log(res);
					}
				})
			}
		},
		onReady() {
			this.$refs['upimg'].chooseImage(6)
		},
		onUnload(){
			console.log('出来')
		}
	}
</script>

<style lang="scss">
	.ny-imgtext-page{
		.ny-main{
			padding-right: 30upx;
			padding-left: 30upx;
		}
		.ny-list-group{
			padding-right: 30upx;
			padding-left: 30upx;
		}
		.ny-picture{
			
		}
	
	}
</style>
