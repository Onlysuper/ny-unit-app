<template>
	<view class="ny-page-space ny-index-page">
		<nyTap @tabChange="tabChange" :typegories="typegories" :top="top" :currentIndex="0"></nyTap>
		<nySearch :show="false" @search="search($event,1)"></nySearch>
		<nyArticlelist :list="artList"></nyArticlelist>
	</view>
</template>


<script>
import nySearch from '@/components/ny-search/search.vue'
import nyTap from '@/components/ny-tap/index.vue'
import nyArticlelist from '@/components/ny-articlelist/index.vue'
var page = 1, type = 0;
export default{
	data() {
		return {
			top : 0,
			//分类信息
			typegories : [
				{typeid : 0, name : "全部"},
				{typeid : 1, name : "精选"},
				{typeid : 2, name : "附近"}
			],
			// 演示文章数据
			artList : []
		};
	},
	components: {
		nyTap,
		nySearch,
		nyArticlelist
	},
	onLoad:function(){
		// #ifdef H5
		this.top = '44px';
		// #endif
		page = 1;
		artList : [];
		this.getNewsList();
	},
	//下拉刷新
	onPullDownRefresh : function(){
		// 重置分页及数据
		page = 1;
		this.artList = [];
		this.getNewsList();
	},
	// 加载更多
	onReachBottom : function(){
		this.getNewsList();
	},
	methods:{
		// 数据和分页是模拟的实际也是这样写
		getNewsList: function(){
			uni.showLoading({});
			// 假设已经到底， 实际根据api接口返回值判断
			if(page >= 3){
				uni.showToast({"title":"已经加载全部", icon:"none"});
				return ;
			}
			uni.request({
				url:'https://www.easy-mock.com/mock/5c8ef1f56336eb1e219105de/ny/article-list?page='+page+'&limit='+'10'+'&type='+type,
				method: 'GET',
				data: {},
				success: res => {
					if(res.data.code=='00'){
						var newsList = res.data.data;
						this.artList = this.artList.concat(newsList);
						uni.hideLoading();
						page++;
					}else{
						// 没有读取到数据
					}
				},
				fail:err=>{
					let errMsg= err.errMsg||'请求失败！'
					uni.showToast({"title":errMsg, icon:"none"});
				},
				complete: res => {
					
					uni.stopPullDownRefresh();
				}
			});
		},
		tabChange : function(obj){
			
			page = 1;
			this.artList = [];
			this.getNewsList();
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
