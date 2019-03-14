<template>
	<view class="ny-page-space ny-message-page">
		<uni-list>
			<uni-swipe-action  @click="deleteHandle" :options="options">
				<uni-list-item title="标题文字" note="描述信息" thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png" show-badge="true" badge-text="12"></uni-list-item>
			</uni-swipe-action>
			<uni-swipe-action  @click="deleteHandle" :options="options">
				<uni-list-item title="标题文字" note="描述信息" thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item>
			</uni-swipe-action>
			<uni-swipe-action  @click="deleteHandle" :options="options">
				<uni-list-item title="标题文字" note="描述信息" thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item>
			</uni-swipe-action>
			<uni-swipe-action  @click="deleteHandle" :options="options">
				<uni-list-item title="标题文字" note="描述信息" thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item></uni-list-item>
			</uni-swipe-action>
		</uni-list>
	</view>
</template>

<script>
	import uniList from '@/components/uni-list/uni-list.vue'
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
	import uniSwipeAction from "@/components/uni-swipe-action/uni-swipe-action.vue"
	export default {
		data() {
			return {
				options: [ {
					text: '删除',
					style: {
						backgroundColor: '#dd524d'
					}
				}]
			}
		},
		components: {uniList,uniListItem,uniSwipeAction},
		onLoad() {

		},
		methods: {
			deleteHandle(){
				console.log('删除');
			}
		}
	}
</script>

<style lang="scss">
	@import "../../style/common.scss";
	.ny-message-page{
		.ny-list-box{
			width: 100%;
			overflow: hidden;
		}
	}
</style>
