<template>
	<view class="container">
		<view class="nav">
			<text>消息</text>
		</view>
		<view class="msg-area">
			<view class="item" v-for="item of 3" :key="item">
				<view class="time">
					<text>
						2021-01-12
					</text>
					<text>
						09:00:00
					</text>
				</view>
				<view class="detail">
					<view class="title">
						<text>
							您有一个新订单
						</text>
						<text>用户张三预定了2021-01-13 09:00 家电安装 项目请及时处理
						</text>
					</view>
				</view>
			</view>
		</view>
		<my-footer :cur="1"></my-footer>
	</view>
</template>

<script>
	import myFooter from '@/components/footer.vue'
	export default {
		components:{
			myFooter
		},
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	.container {
		@include full-screen-color;
		background-color: #F8F8F8;
		overflow-y: auto;

		.nav {
			width: 100%;
			height: 128rpx;
			background: #E94A44;
			@include flexY;
			flex-direction: column-reverse;
			align-items: center;
			justify-self: flex-end;
			
			text {
				@include fontStyle(36rpx, 700, #ffffff, 36rpx);
				margin-bottom: 20rpx;
			}
		}

		.msg-area {
			@include flexY;
			padding:0 30rpx;
			
			.item {
				margin-top: 30rpx;
				@include flexY;
				align-items: center;
				.time {
					
					text {
						@include fontStyle(24rpx, 500, #B5B5B5, 33rpx);

						&:first-of-type {
							margin-right: 20rpx;
						}
					}
					margin-bottom: 20rpx;
				}

				.detail {
					background: #FFFFFF;
					border-radius: 10rpx;
					padding:32rpx;
					box-sizing: border-box;
					.title {
						
						text {
							display: block;

							&:first-of-type {
								@include fontStyle(34rpx, 800, #2E2727, 48rpx);
								margin-bottom: 20rpx;
							}

							&:last-of-type {
								@include fontStyle(28rpx, 400, #B5B5B5, 40rpx);
							}
						}
					}
				}
			}
		}
	}
</style>