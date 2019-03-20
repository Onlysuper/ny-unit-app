<template>
	<view class="ny-user-page">
		<view class="ny-top">
			<view class="ny-user-img">
				<view class="img-back"></view>
			</view>
			<view class="ny-harvest">
				<view class="ny-item">
					<view class="ny-num">4.9w</view>
					<view>获赞</view>
				</view>
				<view class="ny-item">
					<view class="ny-num">100</view>
					<view>关注</view>
				</view>
				<view class="ny-item">
					<view class="ny-num">999w</view>
					<view>粉丝</view>
				</view>
			</view>
		</view>
		<view class="ny-main">
			<nyTap @tabChange="tabChange" :typegories="checkOptions" :top="top" :currentIndex="0"></nyTap>
			<view class="ny-list">
				<view v-if="typeid==0" class="">
					全部
				</view>
				<view v-if="typeid==1" class="">
					精选
				</view>
				<view v-if="typeid==2" class="">
					附近
				</view>
			</view>
		</view>
		
		<!-- <view class="ny-user-top">
			<view class="user-box">
				<view class="img-back"></view>
				<view class="user-context">
					<view class="name">亲宝宝</view>
					<view class="describe">快来完善一下个人信息吧</view>
				</view>
				<uni-icon color="#626466" type="arrowright" size="30"></uni-icon>
				<view class="bb-border-bottom"></view>
			</view>
			<view class="ny-grid-group">
				<view class="ny-grid-item">
					<view class="ny-num">4.9w</view>
					<view>获赞</view>
				</view>
				<view class="ny-grid-item">
					<view class="ny-num">100</view>
					<view>关注</view>
				</view>
				<view class="ny-grid-item">
					<view class="ny-num">999w</view>
					<view>粉丝</view>
				</view>
			</view>
		</view>
		<view class="ny-list-group">
			<uni-list-item class='ny-list' title="收藏"  show-extra-icon="true"  thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png" ></uni-list-item>
			<uni-list-item class='ny-list' title="设置" show-extra-icon="true"  thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item>
			<uni-list-item class='ny-list' title="关于" show-extra-icon="true"  thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item>
		</view> -->
		
		
	</view>
</template>

<script>
	import uniList from '@/components/uni-list/uni-list.vue'
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
	import uniIcon from "@/components/uni-icon/uni-icon.vue"
	import nyTap from '@/components/ny-tap/index.vue'
	export default {
		components: {uniList,uniListItem,uniIcon,nyTap},
		data() {
			return {
				typeid:0,
				top : "0",
				//分类信息
				checkOptions : [
					{typeid : 0, name : "全部"},
					{typeid : 1, name : "精选"},
					{typeid : 2, name : "附近"}
				]
			}
		},
		onLoad() {

		},
		methods: {
			tabChange : function(obj){
				console.log(obj);
				this.typeid = obj.typeid;
				// page = 1;
// 				this.artList = [];
// 				this.getNewsList();
			}
		}
	}
</script>

<style lang="scss">
	 @import "../../style/common.scss";
	 .ny-user-page{
		 .ny-top{
			 @include ny-padding-side();
			 display: flex;
			 flex-direction: row;
			 .ny-user-img{
				 flex: 0 0 120upx;
			 }
			 .ny-harvest{
				 @include ny-flex-row(row);
				 flex: 1;
				 .ny-item{
					 padding: 10upx;
				 }
			 }
		 } 
		 .ny-main{
		 				  @include ny-padding-side();
		 				 .ny-list{
		 					 
		 				 }
		 }
	 }
</style>
