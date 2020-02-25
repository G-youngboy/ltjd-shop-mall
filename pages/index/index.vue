<template>
	<view class="page">
		<!-- 搜索 -->
		<view class="lt-home-search">
			<view class="lt-category">
				<uni-icons type="list" size="22" color="#fff"></uni-icons>
				<view class="lt-category-scale">分类</view>
			</view>
			<view class="lt-rolling-search">
				<icon type="search" size="13" color="#999"></icon>
			</view>
		</view>
		<!-- 轮播图 -->
		<view class="lt-home-banner">
			<!-- 热搜 -->
			<view></view>
			<!-- 轮播图 -->
			<view class="lt-banner-bg">
				<view class="lt-primary-bg lt-route-left"></view>
				<view class="lt-primary-bg lt-route-right"></view>
				<view class="lt-banner-box">
					<swiper indicator-dots="true" autoplay="true" interval="5000" duration="150" class="lt-banner-swiper" circular="{true}">
						<swiper-item v-for="(item, index) in banner" :key="index">
							<image :src="'../../static/banner/' + item" style="width: 100%;height: 260rpx;" mode="scaleToFill"></image>
						</swiper-item>
					</swiper>
				</view>
			</view>
		</view>
		<!-- 产品分类 -->
		<view class="lt-home-category">
			<view class="lt-category-item" v-for="(item, index) in categorys" :key="index">
				<image src="../../static/logo.png" style="width: 80rpx;height: 80rpx;"></image>
				<view style="line-height:24rpx">{{item.title}}</view>
			</view>
		</view>
		<!-- 新人专享 -->
		<view class="lt-home-product lt-white-bg">
			<view class="lt-group-name">
				<view>新人专享</view>
				<uni-icons></uni-icons>
			</view>
			<view class></view>
		</view>
	</view>
</template>

<script>
	import uniIcons from "@/components/uni-icons/uni-icons.vue"
	export default {
		components: {
			uniIcons
		},
		data() {
			return {
				title: 'Hello',
				banner: [
					"1.jpg",
					"2.jpg",
					"3.jpg",
					"4.jpg",
					"5.jpg"
				],
				categorys: [
					{title: '秒杀'},{title: '爆品'},{title: '拼团'},{title: '新品'}
				]
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		/* display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center; */
		background: #333333;
	}
	.lt-home-search {
		width: 100%;
		height: 100rpx;
		padding: 0 30rpx 0 20rpx;
		box-sizing: border-box;
		background: #e41f19;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
		position: fixed;
		left: 0;
		top: 0;
		z-index: 999;
	}
	.lt-category {
		font-size: 24rpx;
		color: #FFFFFF;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		margin: 0;
		margin-right: 22rpx;
		flex-shrink: 0;
	}
	.lt-category-scale {
		transform: scale(0.7);
		line-height: 24rpx;
	}
	.lt-rolling-search {
		width: 100%;
		height: 60rpx;
		border-radius: 35rpx;
		padding: 0 40rpx 0 30rpx;
		box-sizing: border-box;
		background: #FFFFFF;
		display: flex;
		align-items: center;
		flex-wrap: nowrap;
		color: #999;
	}
	.lt-home-banner {
		padding-top: 100rpx;
		box-sizing: border-box;
		background-color: #E41F19;
	}
	.lt-banner-bg {
		display: flex;
		height: 180rpx;
		background: #E41F19;
		position: relative;
	}
	.lt-primary-bg {
		width: 50%;
		display: inline-block;
		height: 224rpx;
		border: 1px solid transparent;
		position: relative;
		z-index: 1;
		background: #E41F19;
	}
	.lt-route-left {
		transform: skewY(8deg);
	}
	.lt-route-right {
		transform: skewY(-8deg);
	}
	.lt-banner-box {
		width: 100%;
		padding: 0 20rpx;
		box-sizing: border-box;
		position: absolute;
		z-index: 99;
		bottom: -80rpx;
		left: 0;
	}
	.lt-banner-swiper {
		width: 100%;
		height: 240rpx;
		border-radius: 12rpx;
		overflow: hidden;
		transform: translateY(0);
	}
	.lt-home-category {
		background: #FFFFFF;
		padding: 80rpx 20rpx 30rpx 20rpx;
		box-sizing: border-box;
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
		font-size: 24rpx;
		color: #555;
		margin-bottom: 30rpx;
	}
	.lt-category-item {
		width: 20%;
		height: 118rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
		flex-direction: column;
		padding-top: 30rpx;
	}
	.lt-home-product {
		margin-top: 20rpx;
		padding: 0 20rpx;
		box-sizing: border-box;
	}
	.lt-white-bg {
		background: #FFFFFF;
	}
	.lt-group-name {
		font-size: 32rpx;
		font-weight: bold;
		text-align: center;
		padding: 20rpx 0;
	}
	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
