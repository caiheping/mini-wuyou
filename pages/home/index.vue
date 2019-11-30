<template>
	<view class="home">
		<!-- 自定义导航栏 -->
		<uni-nav-bar :fixed="true" :statusBar="true" :border="false">
			<!-- 左边 -->
			<block slot="left">
				<view class="nav-left">
					<text>北京</text>
				<uni-icon :size="20" class="uni-icon-wrapper" color="#bbb" type="arrowright" />
				</view>
			</block>
			<!-- 中间 -->
			<view class="nav-tab-bar">
				<block>
					<view class="input-view">
						<uni-icon type="search" size="22" color="#666666" />
						<input confirm-type="search" class="input" type="text" placeholder="输入搜索关键词" @confirm="confirm" />
					</view>
				</block>
			</view>
		</uni-nav-bar>

		<view class="home-body">
			<scroll-view scroll-y :style="{ height: swiperheight + 'px' }">
				<view class="baner">
					<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
						<swiper-item><view class="swiper-item uni-bg-red">A</view></swiper-item>
						<swiper-item><view class="swiper-item uni-bg-green">B</view></swiper-item>
						<swiper-item><view class="swiper-item uni-bg-blue">C</view></swiper-item>
					</swiper>
				</view>
				<view class="menus">
					<view class="item" v-for="(item, index) in 5" :key="index">
						<view class="img">{{ item }}</view>
						<text>谁看过我</text>
					</view>
				</view>
				<view class="recommend">
					<view class="title"><text>为您推荐</text></view>
					<view class="recommend-list">
						<view class="item" v-for="item in 35" :key="item">
							<view class="left">
								<text class="title">中级前端工程师</text>
								<text>阿里巴巴</text>
							</view>
							<view class="right">
								<text class="title">0.8-1.2万</text>
								<text>广州-黄埔</text>
							</view>
						</view>
						<view class="more"><text>了解更多</text></view>
					</view>
				</view>
			</scroll-view>
		</view>
	</view>
</template>

<script>
import uniNavBar from '../../components/uni-nav-bar/uni-nav-bar.vue';
import uniIcon from '@/components/uni-icon/uni-icon.vue';
import uniStatusBar from '@/components/uni-status-bar/uni-status-bar.vue';
export default {
	components: {
		uniNavBar,
		uniIcon,
		uniStatusBar
	},
	data() {
		return {
			tabIndex: 0,
			tabBars: [{ name: '关注', id: 'guanzhu' }],
			swiperheight: 500,
			city: '北京',
			background: ['color1', 'color2', 'color3'],
			indicatorDots: true,
			autoplay: true,
			interval: 2000,
			duration: 500
		};
	},
	methods: {
		back() {
			uni.navigateBack({
				delta: 1
			});
		},
		showMenu() {
			uni.showToast({
				title: '菜单'
			});
		},
		clickLeft() {
			uni.showToast({
				title: '左侧按钮'
			});
		},
		search() {
			uni.showToast({
				title: '搜索'
			});
		},
		showCity() {
			uni.showToast({
				title: '选择城市'
			});
		},
		scan() {
			uni.showToast({
				title: '扫码'
			});
		},
		confirm() {
			uni.showToast({
				title: '搜索'
			});
		},
		changeIndicatorDots(e) {
			this.indicatorDots = !this.indicatorDots;
		},
		changeAutoplay(e) {
			this.autoplay = !this.autoplay;
		},
		intervalChange(e) {
			this.interval = e.target.value;
		},
		durationChange(e) {
			this.duration = e.target.value;
		}
	},
	onPullDownRefresh() {
		console.log('onPullDownRefresh');
		setTimeout(function() {
			uni.stopPullDownRefresh();
			console.log('stopPullDownRefresh');
		}, 1000);
	},
	onLoad() {
		uni.getSystemInfo({
			success: res => {
				let height = res.windowHeight - uni.upx2px(88);
				this.swiperheight = height;
			}
		});
	}
};
</script>
<style scoped lang="scss">
page {
	display: flex;
	flex-direction: column;
	box-sizing: border-box;
	background-color: #efeff4;
}

view {
	font-size: 28upx;
	line-height: inherit;
}
.nav-left{
	display: flex;
	justify-content: center;
	align-items: center;
}
.nav-tab-bar{
	display: flex;
	justify-content: center;
	align-items: center;
	border-radius: 24px;
	border: 1px solid #bebebe;
	.input-view{
		display: flex;
	}
}

.nav {
	height: 44px;
	line-height: 44px;
	text-align: center;
}

.home {
	background: #f2f2f2;
	.home-body {
		border-top: 1px #f5f5f5 solid;
		box-sizing: border-box;
		height: 88rpx;
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

		.input-view {
			.uni-icon {
				line-height: 30px !important;
			}
		}

		.input-view {
			.input {
				margin-top: 10rpx;
				width: 94%;
				padding: 0 3%;
			}
		}
	}
	.baner {
		height: 300upx;
		background: #ffffff;
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

	.menus {
		margin: 20rpx 0;
		padding: 20rpx 0;
		background: #ffffff;
		display: flex;
		color: #999;
		.item {
			flex: 1;
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: center;
			.img {
				background: #007aff;
				border-radius: 4px;
				overflow: hidden;
				width: 100rpx;
				height: 100rpx;
				image {
					width: 100%;
					height: 100%;
				}
			}
			text {
				margin-top: 10rpx;
				text-align: center;
			}
		}
	}
	.recommend {
		background: #ffffff;
		padding: 20rpx 20rpx 0;
		.title {
			display: flex;
			align-items: center;
			justify-content: center;
			text {
				font-weight: bold;
				color: #007aff;
				font-size: 32rpx;
				text-align: center;
			}
		}
		.recommend-list {
			.item {
				display: flex;
				border-bottom: 1rpx solid #f2f2f2;
				justify-content: space-between;
				height: 120rpx;
				.left {
					display: flex;
					flex-direction: column;
					justify-content: center;
					.title {
						font-weight: bold;
						color: #000;
					}
					text {
						color: #999999;
						height: 40rpx;
						line-height: 40rpx;
					}
				}
				.right {
					display: flex;
					flex-direction: column;
					justify-content: center;
					.title {
						font-weight: bold;
						color: #007aff;
					}
					text {
						color: #999999;
						height: 40rpx;
						line-height: 40rpx;
					}
				}
			}
			.more {
				display: flex;
				justify-content: center;
				text {
					line-height: 40px;
					color: #999999;
				}
			}
		}
	}
}
.nav-left > view,
.nav-right > view {
	font-size: 40upx;
}
.nav-left > view {
	color: #ff9619;
}
.nav-left {
	margin-left: 16upx;
}
.nav-right {
	width: 100%;
}
.nav-tab-bar {
	width: 100%;
	margin-left: -20upx;
	position: relative;
}
.nav-tab-bar > view {
	font-size: 32upx;
	padding: 0 15upx;
	font-weight: bold;
	color: #969696;
}
.active {
	color: #333333 !important;
}
.nav-tab-bar-line {
	border-bottom: 5upx solid #fede33;
	border-top: 5upx solid #fede33;
	width: 70upx;
	border-radius: 20upx;
	position: absolute;
	bottom: 12upx;
}
</style>
