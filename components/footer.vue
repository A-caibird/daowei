<template>
	<view class="footer">
		<u-tabbar :value="currentPage" @change="change1" :fixed="true" :placeholder="false" :safeAreaInsetBottom="false"
			activeColor="#2E2727" inactiveColor="#B5B5B5" >
			<u-tabbar-item text="订单" class="item" @click="goTo(0)">
				<image class="u-page__item__slot-icon-image" slot="active-icon" src="/static/index/order_ac.png">
				</image>
				<image class="u-page__item__slot-icon-image" slot="inactive-icon" src="/static/index/order_in.png"></image>
			</u-tabbar-item>
			<u-tabbar-item text="消息" class="item" @click="goTo(1)">
				<image class="u-page__item__slot-icon-image" slot="active-icon" src="/static/index/mes_ac.png">
				</image>
				<image class="u-page__item__slot-icon-image" slot="inactive-icon" src="/static/index/mes_in.png">
				</image>
			</u-tabbar-item>
			<u-tabbar-item text="我的" class="item" @click="goTo(2)">
				<image class="u-page__item__slot-icon-image" slot="active-icon" src="/static/index/mine_ac.png">
				</image>
				<image class="u-page__item__slot-icon-image" slot="inactive-icon" src="/static/index/min_in.png">
				</image>
			</u-tabbar-item>
			
		</u-tabbar>
	</view>
</template>

<script>
	export default {
		props: {
			cur: {
				type: Number,
				require: true
			}
		},
		data() {
			return {
				currentPage: this.cur
			}
		},
		methods: {
			goTo(num) {
				this.currentPage = num;
				switch (num) {
					case 0: {
						uni.navigateTo({
							url: "/pages/my-order/my-order"
						})
						break;
					}
					case 1: {
						uni.navigateTo({
							url:"/pages/message/message"
						})
						break;
					}
					case 2: {
						uni.navigateTo({
							url: "/pages/mine/mine"
						})
						break;
					}
				}
			},
			change1() {

			}
		},
		mounted() {
			// this.curcurrentPage=this.cur;
		}
	}
</script>

<style lang="scss" scoped>
	
	::v-deep .u-page__item__slot-icon-image {
		height:30.24rpx;
		width: 30.24rpx;
	}
	
	::v-deep .data-v-32dc31a4 {
		height:30.24rpx;
		width: 30.24rpx;
	}
	.u-tabbar {
		padding: 20rpx 0;
	}
		
	::v-deep .u-tabbar__content__item-wrapper{
		margin-bottom: 40rpx;
		padding-top: 20rpx;
	}
</style>