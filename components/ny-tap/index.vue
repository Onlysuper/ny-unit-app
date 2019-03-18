<template>
<view class="ny-tag-chose">
	<view class="fixedit" :style="{top:top}">
		<scroll-view class="grace-tab-title grace-center" scroll-x="true" id="grace-tab-title">
			<view v-for="(type, index) in typegories" :key="index" :data-typeid="type.typeid" :data-name="type.name" :data-index="index" :class="[currentIndex_ == index ? 'grace-tab-current' : '']" @tap="tabChange">{{type.name}}</view>
		</scroll-view>
	</view>
</view>
</template>
<style lang="scss">
	.grace-tab{padding:0;}
	.grace-tab-title{white-space:nowrap; text-align:center; background:#FFFFFF;}
	.grace-tab-title view{width:auto; padding:0 12px; margin:0 8px; line-height:42px; display: inline-block; text-align:center; border-bottom:2px solid #FFFFFF; font-size:30upx;}
	.grace-tab-title view:first-child{margin-left: 0;}
	.grace-tab-title view:last-child{margin-right: 0;}
	.grace-tab-current{border-bottom:4upx solid #FF0036 !important; color:#FF0036;}
</style>
<script>
	export default{
		data(){
			return {
				currentIndex_:0
			}
		},
		props:{
			typegories:{
				type:Array,
				default:[]
			},
			top:{
				type:String,
				default:""
			},
			currentIndex:{
				type:Number,
				default:0
			}
		},
		methods:{
			tabChange : function(e){
				// 选中的索引
				var index  = e.currentTarget.dataset.index;
				var typeid = e.currentTarget.dataset.typeid;
				var name = e.currentTarget.dataset.name;
				this.currentIndex_ = index;
				this.$emit("tabChange",{
					typeid:typeid,
					name: name,
					index:index
				});
				
			}
		},
		mounted(){
			this.currentIndex_=this.currentIndex;
		}
	}
</script>