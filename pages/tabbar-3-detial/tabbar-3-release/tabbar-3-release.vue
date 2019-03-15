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
		<uni-list-item class='ny-list' title="谁可以看" show-extra-icon="true"  :extra-icon="{color: '#484e54',size: '21',type: 'locked'}"></uni-list-item>
		<uni-list-item class='ny-list' title="所在位置" show-extra-icon="true"  :extra-icon="{color: '#484e54',size: '21',type: 'location'}"></uni-list-item>
		<uni-list-item class='ny-list' title="记录时间" show-extra-icon="true"  :extra-icon="{color: '#484e54',size: '21',type: 'navigate'}"></uni-list-item>
	</view>
</template>

<script>
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
			uniListItem
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
		.ny-picture{
			
		}
	
	}
</style>
