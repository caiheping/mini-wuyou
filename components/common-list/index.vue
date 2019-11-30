<template>
	<view class="uni-container">
		<view class="uni-panel" v-for="(item, index) in lists" :key="index">
			<view class="uni-panel-h" @click="goDetailPage(item.url)">
				<view class="left">
					<image src="" mode=""></image>
					<text class="uni-panel-text">{{item.name}}</text>
				</view>
				<text class="uni-panel-icon uni-icon">&#xe470;</text>
			</view>
		</view>
	</view>
</template>
<script>
	export default {
		props: {
			lists: {
				type: Array,
				require: true
			}
		},
		onLoad() {},
		onReady() {},
		onShareAppMessage() {
			return {
				title: '欢迎体验uni-app',
				path: '/pages/tabBar/extUI/extUI'
			}
		},
		onNavigationBarButtonTap(e) {
			uni.navigateTo({
				url: '/pages/about/about'
			});
		},
		methods: {
			goDetailPage(path) {
				// uni.navigateTo({
				// 	url: '/pages/extUI/' + path + '/' + path
				// });
			}
		}
	}
</script>

<style scoped lang="scss">
    /* #ifndef APP-PLUS-NVUE */
    page {
        min-height: 100%;
        height: auto;
    }
    /* #endif */
    
    /* 解决头条小程序字体图标不显示问题，因为头条运行时自动插入了span标签，且有全局字体 */
    /* #ifdef MP-TOUTIAO */
    text :not(view) {
        font-family: uniicons;
    }
    /* #endif */
    
    .uni-icon {
        font-family: uniicons;
        font-weight: normal;
    }
    
    .uni-container {
		border-radius: 4px;
		.uni-panel {
			border-bottom: 1px solid #F2F2F2;
			&:last-child{
				border: none;
			}
			.uni-panel-h {
			    background-color: #ffffff;
			    display: flex;
				align-items: center;
			    justify-content: space-between;
			    padding: 12px;
				.left{
					display: flex;
					align-items: center;
					image{
						height: 50rpx;
						width: 50rpx;
						border: 1px solid #F2F2F2;
						margin-right: 20rpx;
						border-radius: 50rpx;
					}
				}
				.uni-panel-text {
				    flex: 1;
				    color: #000000;
				    font-size: 14px;
				    font-weight: normal;
				}
				
				.uni-panel-icon {
				    margin-left: 15px;
				    color: #999999;
				    font-size: 14px;
				    font-weight: normal;
				    transform: rotate(0deg);
				    transition-duration: 0s;
				    transition-property: transform;
				}
			}
			image {
			    width: 80px;
			    height: 80px;
			}
		}
    }
</style>
