<template>
	<view class="user">
		<view class="box-item">
			<view class="item" v-for="(item, index) in itemLists" :key="index">
				<common-list :lists="item.lists"></common-list>
			</view>
		</view>
	</view>
</template>

<script>
	import CommonList from '@/components/common-list/index.vue'
	export default{
		components:{
			CommonList
		},
		data () {
			return{
				itemLists: [
					{
						lists: [
							{
								name: "职位收藏",
								url: "badge"
							},
							{
								name: "申请记录",
								url: "badge"
							},
							{
								name: "不让该公司看我简历",
								url: "badge"
							}
						]
					},
					{
						lists: [
							{
								name: "无忧课堂",
								url: "badge"
							},
							{
								name: "增值服务",
								url: "badge"
							},
							{
								name: "薪酬查询",
								url: "badge"
							}
						]
					},
					{
						lists: [
							{
								name: "用户反馈",
								url: "badge"
							},
							{
								name: "设置",
								url: "badge"
							}
						]
					}
				]
			}
		}
	}
</script>

<style scoped lang="scss">
	.user{
		min-height: 100vh;
		background: #F2F2F2;
		padding: 20rpx;
		box-sizing: border-box;
		.box-item{
			.item{
				margin-bottom: 20rpx;
			}
		}
	}
</style>
