<!-- 上周数据 -->
<template>
	<view>
		<view class="weekly-reward-container" v-for="(item, index) in List" :key='index'>
			<!-- 不显示tag -->
			<view class="tag-content-ul">
				<view class="tag-content-li">
					<view class="tag-num">{{item.time}}</view>
					<text>日期</text>
				</view>
				<view class="tag-content-li">
					<view class="tag-num">{{item.amountLoss}}</view>
					<text>负盈利</text>
				</view>
				<view class="tag-content-li">
					<view class="tag-num colorRed">{{item.amountReward}}</view>
					<text>奖励金(元)</text>
				</view>
			</view>
			<!-- 时间 -->
			<view class="tag-content-time">
				<image class="time-img" src="../../image/time.png" mode="widthFix"></image>
				{{ item.leftTime }}
			</view>
		</view>
	</view>
</template>

<script>
	import tagTitle from '../tag-title.vue'
	export default {
		name: 'weekly-reward',
		components:{
			tagTitle
		},
		props:{
			List:{
				type:Array,
				default:()=>[]
			}
		}
	}
</script>

<style lang="scss" scoped>
.weekly-reward-container{
	background: #fff;
	padding: 10upx 20upx;
	border-radius: 10upx;
}
	.tag-content-ul{
		display: flex;
		border-bottom: 2upx solid #f7f7f7;
		padding: 16upx 0 34upx;
		color: #aaa;
		font-size: 24upx;
	}
	.padding30{
		padding-top: 20upx !important;
	}
	.margin30{
		margin-top: 30upx;
	}
	.tag-content-li{
		flex: 1;
		text-align: center;
	}
	.tag-num{
		font-size: 38upx;
		font-weight: 700;
		font-family: DIN;
		line-height:38upx;
		color: #323233;
		margin-bottom: 10px;
	}
	.fontNone{
		font-weight: 300;
		font-size: 34upx;
		line-height: 20upx;
	}
	.colorRed{
		color: red;
	}
	.tag-content-time{
		// line-height: 68upx;
		display: flex;
		align-items: center;
		height: 68upx;
		font-size: 22upx;
		color: #aaa;
	}
	.time-img{
		width: 24upx;
		height: 24upx;
		margin-right: 8upx;
		vertical-align: middle;
	}
	.tag-none{
		height: 60upx;
		border-bottom: 2upx solid #f7f7f7;
		margin-bottom: 20upx;
	}
	.active{
		color: #333;
		font-weight: 600;
	}
	.timeHeight{
		line-height: 100upx;
		height: 100upx;
	}
</style>
