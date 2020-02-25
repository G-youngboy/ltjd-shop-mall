<template>
	<view class="page">
		<!-- 搜索 -->
		<view class="lt-category-search">
			<view class="lt-search-input">
				<icon type="search" size="13" color="#999"></icon>
				<view style="padding-left: 15rpx;">搜获商品</view>
			</view>
		</view>
		<!-- 左边导航 -->
		<scroll-view scroll-y scroll-with-animation class="tab-view" :scroll-top="scrollTop" :style="{height: menuHeight + 'px'}">
			<view class="tab-item" v-for="(item, index) in tabber" :key="index" :class="currentTab==index ? 'active': ''" @click="handleSwitchItem(index)">
				<text>{{item}}</text>
			</view>
		</scroll-view>
		<!-- 右边详细 -->
		<view class="right-box">
			<view class="right-box-view">
				<swiper autoplay circular interval="5000" duration="150" class="lt-category-swiper">
					<swiper-item v-for="(item, index) in banner" :key="index">
						<image :src="'../../static/banner/' + item" class="slide-image"></image>
					</swiper-item>
				</swiper>
				<view class="lt-category-box">
					<view v-for="(item, index) in categorys" :key="index" class="lt-box-item">
						<image :src="'../../static/' + item" style="height: 120rpx;width: 120rpx;"></image>
						<view style="font-size: 24rpx;">手机</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tabber: ['类型','品跑','电视','空调','洗衣机','冰箱','厨卫大电','厨卫小电','生活电器','个护健康','视听影音'],
				menuHeight: "", //菜单高度
				currentTab: 0, //预设当前项的值
				scrollTop: 0 ,//tab标题的滚动条位置
				banner: [
					"1.jpg",
					"2.jpg",
					"3.jpg",
					"4.jpg",
					"5.jpg"
				],
				categorys: [
					"33.jpg","33.jpg","33.jpg","33.jpg"
				]
			}
		},
		onLoad() {
			uni.getSystemInfo({
				success: (res) => {
					console.log(res);
				}
			})
		},
		methods: {
			// 切换选项卡
			handleSwitchItem(index) {
				if(this.currentTab === index) {
					return true;
				}
				this.currentTab = index;
				// console.log(index);
			}
		}
	}
</script>

<style>
.lt-category-search {
	width: 100%;
	height: 92rpx;
	padding: 0 30rpx;
	background: #FFFFFF;
	border-bottom: 1rpx solid #F1F1F1;
	box-sizing: border-box;
	display: flex;
	flex-direction: row;
	align-items: center;
	justify-content: center;
	position: fixed;
	left: 0;
	top: 0;
	z-index: 999;
}
.lt-search-input {
	width: 100%;
	height: 60rpx;
	background: #F1F1F1;
	border-radius: 30rpx;
	font-size: 26rpx;
	color: #999;
	display: flex;
	justify-content: center;
	align-items: center;
}
.tab-view {
	width: 200rpx;
	height: 100%;
	position: fixed;
	top: 92rpx;
	left: 0;
	z-index: 10;
}
.tab-item {
	width: 200rpx;
	height: 110rpx;
	background: #f6f6f6;
	box-sizing: border-box;
	display: flex;
	align-items: center;
	justify-content: center;
	color: #444;
	font-size: 26rpx;
	font-weight: 400;
}
.active {
	position: relative;
	background: #FFFFFF;
	color: #000000;
	font-size: 30rpx;
	font-weight: 600;
}
.right-box {
	height: 100%;
	background: #FFFFFF;
	padding: 112rpx 20rpx 0 220rpx;
	padding-bottom: env(safe-area-inset-bottom);
	box-sizing: border-box;
}
.right-box-view {
	width: 100%;
	overflow: hidden;
}
.lt-category-swiper {
	width: 100%;
	height: 220rpx;
	border-radius: 12rpx;
	overflow: hidden;
	transform: translateZ(0);
}
.slide-image {
	width: 100%;
	height: 220rpx;
}
.lt-category-box {
	padding-top: 30rpx 20rpx 0;
	width: 100%;
	box-sizing: border-box;
	display: flex;
	display: -webkit-flex;
	justify-content: flex-start;
	flex-direction: row;
	flex-wrap: wrap;
}
.lt-box-item {
	width: 33.3333%;
	text-align: center;
	padding-top: 40rpx;
}
</style>
