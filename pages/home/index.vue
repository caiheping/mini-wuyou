<template>
	<view class="home">
		<uni-status-bar></uni-status-bar>
		<view class="home-body">
			<uni-nav-bar :fixed="false" color="#333333" background-color="#FFFFFF" right-icon="scan" @click-left="showCity" @click-right="scan">
				<block slot="left">
					<view class="city">
						<view>{{ city }}</view>
						<uni-icon type="arrowdown" color="#333333" size="22" />
					</view>
				</block>
				<view class="input-view">
					<uni-icon type="search" size="22" color="#666666" />
					<input confirm-type="search" class="input" type="text" placeholder="输入搜索关键词" @confirm="confirm">
				</view>
			</uni-nav-bar>
			<view class="baner">
				<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
					<swiper-item>
						<view class="swiper-item uni-bg-red">A</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item uni-bg-green">B</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item uni-bg-blue">C</view>
					</swiper-item>
				</swiper>
			</view>
			<view class="menus">
				<view class="item" v-for="(item, index) in 5" :key="index">
					<view class="img">
						{{item}}
					</view>
					<text>谁看过我</text>
				</view>
			</view>
			<view class="recommend">
				<view class="title">
					<text>为您推荐</text>
				</view>
				<view class="recommend-list">
					<view class="item" v-for="item in 5" :key="item">
						<view class="left">
							<text class="title">中级前端工程师</text>
							<text>阿里巴巴</text>
						</view>
						<view class="right">
							<text class="title">0.8-1.2万</text>
							<text>广州-黄埔</text>
						</view>
					</view>
					<view class="more">
						<text>了解更多</text>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue'
	import uniIcon from '@/components/uni-icon/uni-icon.vue'
	import uniStatusBar from '@/components/uni-status-bar/uni-status-bar.vue'
	export default {
		components: {
			uniNavBar,
			uniIcon,
			uniStatusBar
		},
		data() {
			return {
				city: '北京',
				background: ['color1', 'color2', 'color3'],
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500
			}
		},
		methods: {
			back() {
				uni.navigateBack({
					delta: 1
				})
			},
			showMenu() {
				uni.showToast({
					title: '菜单'
				})
			},
			clickLeft() {
				uni.showToast({
					title: '左侧按钮'
				})
			},
			search() {
				uni.showToast({
					title: '搜索'
				})
			},
			showCity() {
				uni.showToast({
					title: '选择城市'
				})
			},
			scan() {
				uni.showToast({
					title: '扫码'
				})
			},
			confirm() {
				uni.showToast({
					title: '搜索'
				})
			},
			changeIndicatorDots(e) {
				this.indicatorDots = !this.indicatorDots
			},
			changeAutoplay(e) {
				this.autoplay = !this.autoplay
			},
			intervalChange(e) {
				this.interval = e.target.value
			},
			durationChange(e) {
				this.duration = e.target.value
			}
		},
		onPullDownRefresh() {
			console.log('onPullDownRefresh')
			setTimeout(function() {
				uni.stopPullDownRefresh()
				console.log('stopPullDownRefresh')
			}, 1000)
		}
	}
</script>
<style scoped lang="scss">
	page {
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
		background-color: #efeff4
	}

	view {
		font-size: 28upx;
		line-height: inherit
	}

	.home{
		background: #F2F2F2;
		.home-body {
			border-top: 1px #f5f5f5 solid;
			.city {
				display: flex;
				flex-direction: row;
				align-items: center;
				justify-content: center;
				width: 100%;
				margin-left: 8px;
				white-space: nowrap;
			}
			
			.input-view {
				width: 92%;
				display: flex;
				background-color: #e7e7e7;
				height: 30px;
				border-radius: 15px;
				padding: 0 4%;
				flex-wrap: nowrap;
				margin: 7px 0;
				line-height: 30px;
				background: #f5f5f5;
			}
			
			.input-view{
				.uni-icon {
					line-height: 30px !important;
				}
			}
			
			.input-view{
				.input {
					margin-top: 10rpx;
					width: 94%;
					padding: 0 3%;
				}
			}
		}
		.baner {
			height: 300upx;
			background: #FFFFFF;
			.swiper {
				height: 300upx;
			}
			.swiper-item {
				display: block;
				height: 300upx;
				line-height: 300upx;
				text-align: center;
			}
		}
		
		.menus{
			margin: 20rpx 0;
			padding: 20rpx 0;
			background: #FFFFFF;
			display: flex;
			color: #999;
			.item{
				flex: 1;
				display: flex;
				flex-direction: column;
				align-items: center;
				justify-content: center;
				.img{
					background: #007AFF;
					border-radius: 4px;
					overflow: hidden;
					width: 100rpx;
					height: 100rpx;
					image{
						width: 100%;
						height: 100%;
					}
				}
				text{
					margin-top: 10rpx;
					text-align: center;
				}
			}
		}
		.recommend{
			background: #FFFFFF;
			padding: 20rpx 20rpx 0;
			.title{
				display: flex;
				align-items: center;
				justify-content: center;
				text{
					font-weight: bold;
					color: #007AFF;
					font-size: 32rpx;
					text-align: center;
				}
			}
			.recommend-list{
				.item{
					display: flex;
					border-bottom: 1rpx solid #F2F2F2;
					justify-content: space-between;
					height: 120rpx;
					.left{
						display: flex;
						flex-direction: column;
						justify-content: center;
						.title{
							font-weight: bold;
							color: #000;
						}
						text{
							color: #999999;
							height: 40rpx;
							line-height: 40rpx;
						}
					}
					.right{
						display: flex;
						flex-direction: column;
						justify-content: center;
						.title{
							font-weight: bold;
							color: #007AFF;
						}
						text{
							color: #999999;
							height: 40rpx;
							line-height: 40rpx;
						}
					}
				}
				.more{
					display: flex;
					justify-content: center;
					text{
						line-height: 40px;
						color: #999999;
					}
				}
			}
		}
	}
</style>