<template>
	<view class="resume">
		<uni-nav-bar :backgroundColor="bg" :fixed="true" :statusBar="true" :border="false">
			<!-- 右边 -->
			<block slot="right">
				<view class="nav-right">
					<text>中文</text>
				</view>
			</block>
		</uni-nav-bar>
		<scroll-view scroll-y :style="{height:swiperheight+'px'}">
			<view>
				<view class="top-base">
					<view class="box">
						<text class="title">我的简历</text>
						<view class="content">
							<view class="top">
								<view class="finish">
									<text>简历完善程度: 77%</text>
								</view>
								<view class="secrecy">
									<text>完全保密</text>
								</view>
							</view>
							<view class="options">
								<view class="item">
									<text>设置</text>
								</view>
								<view class="item">
									<text>刷新</text>
								</view>
								<view class="item">
									<text>预览</text>
								</view>
							</view>
						</view>
					</view>
				</view>
				<view class="resume-content">
					<view class="base-info">
						<uni-list-item title="基本信息" />
						<view class="content">
							<view class="img">img</view>
							<view class="info">
								<view>
									<text>特斯</text>|男|23岁
								</view>
								<view>
									<text>广州</text>|2年工作经验
								</view>
								<view>
									<text>13711021233</text>
								</view>
								<view>
									<text>34324223@qq.com</text>
								</view>
								<view>
									<text>目前正在找工作</text>
								</view>
							</view>
						</view>
					</view>
					<view class="intention">
						<uni-list-item title="求职意向" />
						<view class="content">
							<view class="info">
								<view>
									<text>职能</text>
									<text>Web 前端</text>
								</view>
								<view>
									<text>工作地点</text>
									<text>广州</text>
								</view>
								<view>
									<text>期望薪资</text>
									<text>4000-6000</text>
								</view>
								<view>
									<text>个人标签</text>
									<text>积极乐观</text>
								</view>
							</view>
						</view>
					</view>
					<view class="work-experience">
						<uni-list-item title="工作经验" />
						<view class="content">
							<view class="work">
								<view>
									<text>2017/10-至今</text>
								</view>
								<view>阿里巴巴集团</view>
								<view>web开发</view>
							</view>
							<view class="work">
								<view>
									<text>2016/10-2017-09</text>
								</view>
								<view>阿里巴巴集团</view>
								<view>web开发</view>
							</view>
						</view>
					</view>
					<view class="project-experience">
						<uni-list-item title="项目经验" />
						<view class="content">
							<view class="project">
								<view>
									<text>2017/10-至今</text>
								</view>
								<view>阿里巴巴项目</view>
							</view>
							<view class="project">
								<view>
									<text>2016/10-2017/08</text>
								</view>
								<view>微信小程序</view>
							</view>
							<view class="project">
								<view>
									<text>2012/10-2014/01</text>
								</view>
								<view>王者荣耀</view>
							</view>
						</view>
					</view>
					<view class="education">
						<uni-list-item title="教育经历" />
						<view class="content">
							<view class="school">
								<view>
									<text>2016/10-2017-09</text>
								</view>
								<view>北京大学</view>
								<view>本科/计算机应用</view>
							</view>
						</view>
					</view>
				</view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	import uniNavBar from '../../components/uni-nav-bar/uni-nav-bar.vue';
	import uniList from '@/components/uni-list/uni-list.vue'
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
	export default{
		data () {
			return{
				swiperheight:500,
				bg: '#ff6666'
			}
		},
		components:{
			uniNavBar,
			uniListItem
		},
		onLoad() {
			uni.getSystemInfo({
				success: res => {
					let height = res.windowHeight - uni.upx2px(88);
					this.swiperheight = height;
				}
			});
		}
	}
</script>

<style scoped lang="scss">
	.nav-right{
		color: #FFFFFF;
	}
	.resume{
		position: relative;
		.top-base{
			position: relative;
			.box{
				background: #FFFFFF;
				padding: 20rpx;
				box-sizing: border-box;
				border-radius: 10rpx;
				box-shadow: 0 0 20rpx #CCCCCC;
				.title{
					font-size: 32rpx;
				}
				.content{
					.top{
						display: flex;
						font-size: 34rpx;
						color: #999999;
						text{
							margin-right: 30rpx;
						}
					}
					.options{
						display: flex;
						.item{
							display: flex;
							flex: 1;
							justify-content: center;
							align-items: center;
							color: #666666;
						}
					}
				}
			}
		}
		.resume-content{
			padding: 30rpx 30rpx 0 30rpx;
			position: relative;
			.base-info{
				background: #FFFFFF;
				box-sizing: border-box;
				border-radius: 10rpx;
				box-shadow: 0 0 20rpx #CCCCCC;
				margin-bottom: 30rpx;
				.content{
					display: flex;
					padding: 20rpx;
					.img{
						width: 100rpx;
						height: 100rpx;
						margin-right: 20rpx;
					}
					.info{
						
					}
				}
			}
			.intention{
				background: #FFFFFF;
				box-sizing: border-box;
				border-radius: 10rpx;
				box-shadow: 0 0 20rpx #CCCCCC;
				margin-bottom: 30rpx;
				.content{
					display: flex;
					padding: 20rpx;
					.info{
						view{
							text{
								margin: 0 16rpx;
							}
						}
					}
				}
			}
			.work-experience{
				background: #FFFFFF;
				box-sizing: border-box;
				border-radius: 10rpx;
				box-shadow: 0 0 20rpx #CCCCCC;
				margin-bottom: 30rpx;
				.content{
					margin: 20rpx;
					position: relative;
					&:before{
						content: '';
						height: calc(100% - 10rpx);
						width: 1rpx;
						background: #007AFF;
						position: absolute;
						left: 0;
						top: 10rpx;
					}
					.work{
						padding-left: 30rpx;
						margin: 20rpx 0;
						box-sizing: border-box;
						position: relative;
						&:before{
							content: '';
							height: 21rpx;
							width: 21rpx;
							background: #09BB07;
							border-radius: 50%;
							position: absolute;
							left: -10rpx;
							top: 10rpx;
						}
					}
				}
			}
			.project-experience{
				background: #FFFFFF;
				box-sizing: border-box;
				border-radius: 10rpx;
				box-shadow: 0 0 20rpx #CCCCCC;
				margin-bottom: 30rpx;
				.content{
					margin: 20rpx;
					position: relative;
					&:before{
						content: '';
						height: calc(100% - 10rpx);
						width: 1rpx;
						background: #007AFF;
						position: absolute;
						left: 0;
						top: 10rpx;
					}
					.project{
						padding-left: 30rpx;
						margin: 20rpx 0;
						box-sizing: border-box;
						position: relative;
						&:before{
							content: '';
							height: 21rpx;
							width: 21rpx;
							background: #09BB07;
							border-radius: 50%;
							position: absolute;
							left: -10rpx;
							top: 10rpx;
						}
					}
				}
			}
			.education{
				background: #FFFFFF;
				box-sizing: border-box;
				border-radius: 10rpx;
				box-shadow: 0 0 20rpx #CCCCCC;
				margin-bottom: 30rpx;
				.content{
					margin: 20rpx;
					position: relative;
					&:before{
						content: '';
						height: calc(100% - 10rpx);
						width: 1rpx;
						background: #007AFF;
						position: absolute;
						left: 0;
						top: 10rpx;
					}
					.school{
						padding-left: 30rpx;
						margin: 20rpx 0;
						box-sizing: border-box;
						position: relative;
						&:before{
							content: '';
							height: 21rpx;
							width: 21rpx;
							background: #09BB07;
							border-radius: 50%;
							position: absolute;
							left: -10rpx;
							top: 10rpx;
						}
					}
				}
			}
		}
	}
</style>
