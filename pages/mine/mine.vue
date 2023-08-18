<template>
	<view class="container">
		<view class="head">
			<view class="nav">
				<text>
					我的
				</text>
				<image src="@/static/set.png">

				</image>
			</view>
			<view class="avatar-area">
				<view class="left">
					<view class="image-box">
						<image src="@/static/avatar.png">
						</image>
					</view>
					<view class="text-info">
						<view class="up">
							<text>伟大的技师</text>
							<image src="@/static/whiteRight.png"></image>
						</view>
						<view class="down">
							<text>
								已实名
							</text>
						</view>
					</view>
				</view>
				<view class="right">
					<image>
					</image>
				</view>
			</view>

			<view class="person-info">
				<view class="item">
					<text>
						100
					</text>
					<text>
						关注
					</text>
				</view>
				<view class="item">
					<text>
						98
					</text>
					<text>
						成功接单
					</text>
				</view>
				<view class="item">
					<text>
						100
					</text>
					<text>
						好评率
					</text>
				</view>
				<view class="item">
					<text>
						10
					</text>
					<text>
						退款率
					</text>
				</view>
			</view>

			<view class="function">
				<view class="box">
					<view class="item">
						<image src="@/static/mine/event.png">

						</image>
						<text>
							服务项目
						</text>
					</view>
					<view class="item">
						<image src="@/static/mine/time.png">

						</image>
						<text>
							服务时间
						</text>
					</view>
					<view class="item">
						<image src="@/static/mine/area.png">

						</image>
						<text>
							服务区域
						</text>
					</view>
				</view>
			</view>
		</view>
		<view class="person-select">
			<view class="item">
				<view class="left">
					<image src="@/static/mine/tuorist.png">

					</image>
					<text>
						新手指引
					</text>
				</view>
				<view class="right">
					<image>

					</image>
				</view>
			</view>
			<view class="divi">

			</view>
			<view class="item">
				<view class="left">
					<image src="@/static/mine/comment.png">

					</image>
					<text>
						用户评价
					</text>
				</view>
				<view class="right">
					<image>

					</image>
				</view>
			</view>
			<view class="divi">

			</view>
			<view class="item">
				<view class="left">
					<image src="@/static/mine/feedback.png">

					</image>
					<text>
						意见反馈
					</text>
				</view>
				<view class="right">
					<image>

					</image>
				</view>
			</view>
			<view class="divi">

			</view>
			<view class="item">
				<view class="left">
					<image src="@/static/mine/about.png">

					</image>
					<text>
						关于我们
					</text>
				</view>
				<view class="right">
					<image>

					</image>
				</view>
			</view>
		</view>
		<view class="ad">
			<image src="@/static/mine/ad.png">
			</image>
		</view>
		<my-footer :cur="2"></my-footer>
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
		background-color: #ffffff;
		overflow-y: auto;
		padding-bottom: 1000rpx;

		.head {
			width: 100%;

			&::after {
				content: "";
				position: absolute;
				top: 0;
				left: 0;
				background-color: red;
				width: 100%;
				height: 612rpx;
			}

			.nav {
				position: relative;
				top: 100rpx;
				z-index: 1;

				text {
					@include fontStyle(36rpx, 700, #ffffff, 36rpx);
					position: absolute;
					left: 50%;
					transform: translateX(-50%);

				}

				image {
					width: 40rpx;
					height: 40rpx;
					float: right;
					margin-right: 47rpx;
				}
			}

			.avatar-area {
				width: 100%;
				position: relative;
				top: 150rpx;
				z-index: 1;
				@include flexX;
				justify-content: space-between;
				padding-left: 76rpx;
				padding-right: 48rpx;
				box-sizing: border-box;

				.left {
					@include flexX;
					align-items: center;


					.image-box {
						margin-right: 30rpx;

						image {
							width: 120rpx;
							height: 120rpx;
							border-radius: 50%;
						}
					}

					.text-info {

						.up {
							@include flex;
							align-items: center;

							text {
								@include fontStyle(36rpx, 700, #ffffff, 50rpx);
							}

							image {
								width: 24rpx;
								height: 24rpx;
							}
						}

						.down {
							text {
								@include fontStyle(24rpx, 400, #ffffff, 33rpx);
							}
						}
					}
				}

				.right {
					image {
						width: 80rpx;
						height: 80rpx;
						background: #ffffff;
					}
				}
			}

			.person-info {
				width: 100%;
				position: relative;
				top: 180rpx;
				z-index: 1;
				@include flexX;
				box-sizing: border-box;
				justify-content: space-between;
				padding: 0 98rpx;

				.item {
					@include flexY;
					align-items: center;

					text {
						display: block;

						&:first-of-type {
							@include fontStyle(32rpx, 600, #ffffff, 45rpx);
						}

						&:last-of-type {
							@include fontStyle(22rpx, 400, #ffffff, 30rpx);
						}
					}
				}
			}

			.function {
				box-sizing: border-box;
				z-index: 2;
				position: relative;
				top: 200rpx;
				width: 100%;
				height: 200rpx;
				padding: 30rpx 30rpx;

				.box {
					width: 100%;
					height: 200rpx;
					box-sizing: border-box;
					box-shadow: 0rpx 3rpx 34rpx 0rpx rgba(196, 169, 169, 0.46);
					border-radius: 20rpx;
					background: #FFFFFF;
					@include flexX;
					padding: 36rpx 53rpx 19rpx 53rpx;
					justify-content: space-between;

					.item {
						@include flexY;
						align-items: center;

						image {
							width: 82rpx;
							height: 102rpx;
						}

						text {
							@include fontStyle(28rpx, 400, #696565, 40rpx);
						}

					}
				}
			}
		}

		.person-select {
			position: relative;
			top: 280rpx;
			width: 100%;
			padding: 0 40rpx;
			box-sizing: border-box;

			.item {
				@include flexX;
				align-items: center;
				justify-content: space-between;

				.left {
					@include flexX;
					align-items: center;

					image {
						width: 64rpx;
						height: 64rpx;
						margin-right: 20rpx;
					}

					text {
						@include fontStyle(30rpx, 500, #2E2727, 42rpx);
					}
				}

				.right {
					image {
						width: 11rpx;
						height: 20rpx;
						background: #B2B2B2;
					}
				}
			}

			.divi {
				background: #E0E0E0;
				width: 100%;
				height: 1rpx;
				margin: 30rpx 0;
			}
		}

		.ad {
			position: relative;
			top:360rpx;
			padding: 0 40rpx;
			box-sizing: border-box;
			// z-index: 10;
			image {
				width: 670rpx;
				height: 180rpx;
			}
		}
	}
</style>