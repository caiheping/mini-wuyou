<template>
	<view class="message">
		<view class="item">
			<image src="" mode=""></image>
			<text>
				谁看过我
			</text>
		</view>
		<view class="item">
			<image src="" mode=""></image>
			<text>
				无忧小助手
			</text>
		</view>
	</view>
</template>

<style lang="scss" scoped>
	.message{
		min-height: 100vh;
		background: #F2F2F2;
		.item{
			background: #FFFFFF;
			display: flex;
			align-items: center;
			padding: 20rpx;
			border-bottom: 1px solid #F2F2F2;
			image{
				width: 100rpx;
				height: 100rpx;
				border-radius: 50%;
				border: 1px solid red;
				margin-right: 20rpx;
			}
			text{
				color: #333333;
			}
		}
	}
</style>