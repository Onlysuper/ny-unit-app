<template>
	<view class="ny-imgtext-page">
		<view class="ny-main">
			<view class="ny-content">
				 <textarea placeholder="说点什么吧" @blur="bindTextAreaBlur" auto-height />
			</view>
			<view class="ny-picture">
				<sunsin-upimg url="https://xxx" :count="6" :autoup="false" @onUpImg="upImgData" />
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
	import sunsinUpimg from '@/components/sunsin-upimg/sunsin-upimg.vue'
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		components: {
			sunsinUpimg,
			uniListItem,
			uniTag
		},
		onLoad() {

		},
		//获取上传图片的所有信息,为数组
		upImgData(e){
			console.log('来了,伙计',e)
		},
		methods: {
			bindTextAreaBlur: function (e) {
				console.log(e.detail.value)
			}
		}
	}
</script>

<style lang="scss">
	.ny-imgtext-page{
		.ny-main{
			padding-right: 30rpx;
			padding-left: 30rpx;
		}
		.ny-list-group{
			padding-right: 30rpx;
			padding-left: 30rpx;
		}
		.ny-picture{
			
		}
	
	}
</style>
