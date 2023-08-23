<template>
	<view class="container " :class="{active:share}">
		<view class="head">
			<view class="nav">
				<text>
					我的
				</text>
				<image src="@/static/set.png" @tap="goTo('set')">

				</image>
			</view>
			<view class="avatar-area">
				<view class="left">
					<view class="image-box">
						<image src="@/static/avatar.png">
						</image>
					</view>
					<view class="text-info">
						<view class="up" @tap="goTo('personInfo')">
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
				<view class="right" @tap="open">
					<image src="@/static/mine/qr.png">
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
					<view class="item" @tap="goTo('服务项目')">
						<image src="@/static/mine/event.png">

						</image>
						<text>
							服务项目
						</text>
					</view>
					<view class="item" @tap="goTo('服务时间')">
						<image src="@/static/mine/time.png">

						</image>
						<text>
							服务时间
						</text>
					</view>
					<view class="item" @tap="goTo('服务区域')">
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
			<view class="item" @tap="goTo('意见反馈')">
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
			<view class="item" @tap="goTo('关于我们')">
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
		<template v-if="share">
			<view class="popCenter">
				<view class="avatar">
					<view class="left">
						<view class="image-box">
							<image src="@/static/avatar.png">
							</image>
						</view>
						<view class="text-info">
							<view class="up" @tap="goTo('personInfo')">
								<text>伟大的技师</text>
								<image src="@/static/whiteRight.png"></image>
							</view>
							<view class="down">
								<image></image>
								<text>维修中心</text>
							</view>
						</view>
					</view>
				</view>
				<view class="des">
					<text>
						5年技师经验，擅长维修各个家电类型，洗衣机，空调，电视，冰箱，热水器，油烟机等等
					</text>
				</view>
				<view class="qr">
					<image>

					</image>
				</view>
				<view class="jia">
					<text>
						扫一扫加好友
					</text>
				</view>
			</view>
		</template>
		<template v-if="share">
			<view class="popBottom">
				<view class="method">
					<view class="one" style="">
						<image src="@/static/pyq.png">

						</image>
						<text>
							微信朋友圈
						</text>
					</view>
					<view class="one">
						<image src="@/static/weChat.png">

						</image>
						<text>
							微信好友
						</text>
					</view>
				</view>
				<view class="divi">
				</view>
				<view class="bottom" @tap="cancelShare">
					<text>
						取消
					</text>
				</view>
			</view>
		</template>

		<my-footer :cur="2"></my-footer>
	</view>
</template>

<script>
	import myFooter from '@/components/footer.vue'
	export default {
		components: {
			myFooter
		},
		data() {
			return {
				share: false
			}
		},
		methods: {
			cancelShare(){
				this.share = false;
			},
			open() {
				this.share = true;
			},
			goTo(str) {
				if (str == '关于我们') {
					uni.navigateTo({
						url: '/pages/aboutUs/aboutUs',
						success: res => {},
						fail: () => {},
						complete: () => {}
					});
				} else if (str == '意见反馈') {
					uni.navigateTo({
						url: '/pages/feedback/feedback',
						success: res => {},
						fail: () => {},
						complete: () => {}
					});
				} else if (str == '服务项目') {
					uni.navigateTo({
						url: '/pages/server-event/server-event',
						success: res => {},
						fail: () => {},
						complete: () => {}
					});
				} else if (str == '服务时间') {
					uni.navigateTo({
						url: '/pages/server-time/server-time',
						success: res => {},
						fail: () => {},
						complete: () => {}
					});
				} else if (str == '服务区域') {
					uni.navigateTo({
						url: '/pages/server-location/server-location',
						success: res => {},
						fail: () => {},
						complete: () => {}
					});
				} else if (str == 'set') {
					uni.navigateTo({
						url: '/pages/set/set',
						success: res => {},
						fail: () => {},
						complete: () => {}
					});
				} else if (str == 'personInfo') {
					uni.navigateTo({
						url: '/pages/personal-info/personal-info',
						success: res => {},
						fail: () => {},
						complete: () => {}
					});
				}
			}
		}
	}
</script>

<style lang="scss" scoped>
	.container {
		@include full-screen-color;
		background-color: #ffffff;
		overflow-y: auto;
		padding-bottom: 1000rpx;

		&.active {
			overflow-y: auto;
			padding-bottom: 0rpx;

			&::after {
				content: '';
				position: absolute;
				top: 0;
				bottom: 0;
				right: 0;
				left: 0;
				background: #000000;
				opacity: 0.5;
				z-index: 2;
			}
		}

		.head {
			width: 100%;

			&::after {
				content: "";
				position: absolute;
				top: 0;
				left: 0;
				background: url('/static/bg.png');
				background-size: cover;
				background-repeat: no-repeat;
				background-position: center center;
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
				align-items: center;

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
								border: 2rpx solid #FFFFFF;
								border-radius: 26rpx;
								padding: 2rpx 10rpx;
								padding-top: 0rpx;
							}
						}
					}
				}

				.right {
					image {
						width: 80rpx;
						height: 80rpx;
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
						width: 24rpx;
						height: 24rpx;
						background: red;
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
			top: 360rpx;
			text-align: center;

			image {
				width: 670rpx;
				height: 180rpx;
			}
		}

		.popCenter {
			position: fixed;
			width: 560rpx;
			background: #F8F8F8;
			border-radius: 10rpx;
			top: 274rpx;
			left: 50%;
			transform: translate3d(-50%, 0, 0);
			z-index: 100;

			&::after {
				content: '';
				position: absolute;
				top: 0;
				left: 0;
				width: 100%;
				height: 364rpx;
				z-index: -1;
				background: url('/static/bg.png');
				background-size: cover;
				background-repeat: no-repeat;
				background-position: center center;
			}

			.avatar {
				width: 100%;
				margin-top: 41rpx;
				@include flexX;
				justify-content: space-between;
				padding-left: 40rpx;
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
							@include flexX;
							align-items: center;

							image {
								width: 32rpx;
								height: 32rpx;
								margin-right: 10rpx;
								background-color: red;
							}

							text {
								@include fontStyle(28rpx, 400, #ffffff, 40rpx);
							}
						}
					}
				}

				.right {
					image {
						width: 80rpx;
						height: 80rpx;
					}
				}
			}

			.des {
				padding: 0 40rpx;

				text {
					@include fontStyle(22rpx, 400, #DDDDDD, 27rpx);
				}
			}

			.qr {
				position: relative;
				left: 50%;
				margin-top: 33rpx;
				transform: translate(-50%);
				background: #FFFFFF;
				border-radius: 10rpx;
				box-sizing: border-box;
				padding: 32rpx 19rpx;
				padding-bottom: 20rpx;
				text-align: center;
				display: inline-block;

				image {
					width: 442rpx;
					height: 442rpx;
					background-color: red;

				}
			}

			.jia {
				text-align: center;
				margin-top: 20rpx;
				margin-bottom: 25rpx;

				text {
					@include fontStyle(24rpx, 400, #B5B5B5, 33rpx);
				}
			}
		}

		.popBottom {
			position: fixed;
			bottom: 0;
			left: 0;
			right: 0;
			background: #ffffff;
			width: 100%;
			z-index: 20000000000000000000;

			.method {
				width: 100%;
				padding: 41rpx 73rpx;
				box-sizing: border-box;
				@include flexX;

				.one {
					@include flexY;
					align-items: center;
					margin-right: 64rpx;

					image {
						width: 100rpx;
						height: 100rpx;
						margin-bottom: 12rpx;
					}

					text {
						@include fontStyle(22rpx, 400, #999999, 30rpx);
					}
				}
			}

			&>.divi {
				height: 1rpx;
				background: #DDDDDD;
			}

			.bottom {
				text-align: center;
				padding: 32rpx 0;

				text {
					@include fontStyle(30rpx, 500, #2E2727, 42rpx);
				}
			}
		}
	}
</style>