<template>
	<view class="ny-page-space ny-index-page">
		<view class="ny-tag-chose">
			<!-- glance 滑动导航栏组件 -->
			<TabBar
				topfixedval='0px' 
				:topfixed=true 
				@clickitem="clickitem" 
				:data = "[{textcontent:'关注'},
						{textcontent:'发现'},
						{textcontent:'附近'}]">
			</TabBar>
		</view>
		<view class="ny-top-search">
			<mSearch :show="false" @search="search($event,1)"></mSearch>
		</view>
		<view class="ny-list-container">
			<navigator url="/pages/index/detail">
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
			</navigator>
		</view>
	</view>
</template>

<script>
	import mSearch from "@/components/mehaotian-search/mehaotian-search.vue" 
	import TabBar from "@/components/wxcomponents/glance-SlideNavTabBar/glance-SlideNavTabBar.vue" 
	export default {
		data() {
			return {
            val1: ''
			}
		},
		components: {  
			mSearch,
			TabBar
		},
		onLoad() {

		},
		methods: {
			search(e, val) {
				console.log(e, val);
				this['val'+val] = e;
			},
			clickitem(obj){
				console.log(obj)
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
