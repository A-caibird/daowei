<template>
	<view class="container">
		<view class="head">
			<view class="nav">
				<image src="@/static/back.png" @tap="back">

				</image>
				<text>
					订单详情
				</text>
			</view>
			<view class="state">
				<view class="left">
					<text>
						订单进行中
					</text>
					<text>
						02:00:00
					</text>
				</view>
				<view class="right">
					<text>
						路线查询
					</text>
					<image>

					</image>
				</view>
			</view>
		</view>
		<view class="appointment-details">
			<view class="time">
				<text>预约时间：</text>
				<text>2021-01-03</text>
				<text>（周日）</text>
				<text>19:00</text>
			</view>
			<view class="divi">
			</view>
			<view class="person">
				<text>预 约 人： </text>
				<text>张三</text>
				<text>13809090090</text>

			</view>
			<view class="divi">
			</view>
			<view class="adress">
				<text>预约地址： </text>
				<text>宁波鄞州区南峪校区二期恒业大厦3幢10 </text>
			</view>
			<view class="divi" style="background: transparent;">
			</view>
		</view>
		<view class="eventDetail">
			<view class="content-info">

				<view class="left">
					<image>

					</image>
					<view class="textinfo">
						<text>
							油烟机清洗
						</text>
						<text>
							热水器维修一口价，所有费用严格按..
						</text>
					</view>
				</view>
				<view class="right">
					<text>
						30.00元
					</text>
					<text>
						*3
					</text>
				</view>
			</view>

			<view class="price">
				<text>共3件</text>
				<text>实付金额:</text>
				<text>30.00元</text>
			</view>
		</view>
		<view class="order-info">
			<view class="item">
				<text>
					订单编号
				</text>
				<text>
					210990343490809
				</text>
			</view>
			<view class="divi">

			</view>
			<view class="item">
				<text>
					订单备注
				</text>
				<text>
					请准时到达
				</text>
			</view>
		</view>
		<view class="footer">
			<view class="btn">
				<text>
					联系用户
				</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			back() {
				uni.navigateBack()
			}
		}
	}
</script>

<style lang="scss" scoped>
	.container {
		@include full-screen-color;
		background-color: #F8F8F8;
		overflow-y: auto;

		.head {
			width: 100%;
			height: 328rpx;
			background: #E94A44;
			box-sizing: border-box;
			padding: 0 22rpx;

			.nav {
				position: relative;
				top: 100rpx;
				width: 100%;

				image {
					width: 32rpx;
					height: 32rpx;
					position: absolute;
					left: 0;
				}

				text {
					@include fontStyle(36rpx, 1000, #ffffff, 36rpx);
					position: absolute;
					left: 50%;
					transform: translateX(-50%);
				}
			}

			.state {
				@include flexX;
				justify-content: space-between;
				position: relative;
				top: 200rpx;
				padding: 0 28rpx;
				box-sizing: border-box;

				.left {
					text {
						@include fontStyle(32rpx, 6800, #ffffff, 45rpx);
						display: block;
					}
				}

				.right {
					image {
						background-color: red;
						width: 24rpx;
						height: 24rpx;
						margin-left: 10rpx;
					}

					text {
						@include fontStyle(28rpx, 600, #ffffff, 40rpx);
					}
				}
			}
		}

		.appointment-details {


			background: #ffffff;
			padding: 0 50rpx;
			padding-top: 27rpx;
			box-sizing: border-box;

			.divi {
				width: 100%;
				height: 1rpx;
				margin: 27rpx 0;
				background: #E0E0E0;
			}

			.time {
				text {
					@include fontStyle(28rpx, 400, #E94A44, 40rpx);

					&:first-of-type {
						display: inline-block;
						width: 140rpx;
						@include fontStyle(28rpx, 400, #2E2727, 40rpx);
					}

					&:nth-of-type(3) {
						display: inline-block;
						margin: 0 10rpx;
					}
				}
			}

			.person {
				margin-top: 10rpx;

				text {
					@include fontStyle(28rpx, 400, #2E2727, 40rpx);


					&:first-of-type {
						@include fontStyle(28rpx, 400, #2E2727, 40rpx);
						display: inline-block;
						width: 140rpx;
					}

					&:nth-of-type(3) {
						margin: 0 10rpx;
					}
				}
			}

			.adress {
				width: 100%;
				@include flexX;
				margin-top: 10rpx;

				text {
					@include fontStyle(28rpx, 400, #E94A44, 40rpx);

					&:first-of-type {
						@include fontStyle(28rpx, 400, #2E2727, 40rpx);
						display: inline-block;
						width: 140rpx;
					}

					&:nth-of-type(2) {
						@include fontStyle(28rpx, 400, #2E2727, 40rpx);
						white-space: pre-wrap;
					}
				}

				.right {}
			}
		}

		.eventDetail {
			margin-top: 27rpx;
			background: #ffffff;
			padding: 0 50rpx;
			box-sizing: border-box;
			position: relative;
			@include flexY;

			.content-info {
				@include flexX;
				position: relative;
				justify-content: space-between;
				margin-top: 20rpx;

				.left {
					@include flexX;
					align-items: flex-start;

					image {
						width: 120rpx;
						height: 120rpx;
						border-radius: 10rpx;
						background: #666666;
						margin-right: 20rpx;
					}

					.textinfo {
						text {
							@include fontStyle(28rpx, 800, #2E2727, 40rpx);
							display: block;
							width: 306rpx;

							&:last-of-type {
								@include fontStyle(24rpx, 400, #919191, 33rpx);

							}

							&:first-of-type {
								margin-bottom: 20rpx;
							}
						}
					}
				}

				.right {
					position: absolute;
					right: 0;

					text {
						@include fontStyle(24rpx, 400, #919191, 33rpx);
						display: block;


						&:first-of-type {
							@include fontStyle(24rpx, 400, #696565, 33rpx);
							margin-bottom: 40rpx;

						}
					}
				}
			}

			.price {
				// float:right;
				margin-top: 50rpx;
				align-self: flex-end;
				margin-bottom: 30rpx;

				text {
					@include fontStyle(22rpx, 400, #666666, 30rpx);

					&:nth-of-type(1) {
						margin-right: 18rpx;
					}

					&:nth-of-type(2) {
						margin-right: 18rpx;
					}

					&:nth-of-type(3) {
						@include fontStyle(28rpx, 800, #E94A44, 40rpx);
					}
				}
			}
		}

		.order-info {
			background: #ffffff;
			margin-top: 27rpx;
			padding: 20rpx 50rpx;

			.divi {
				width: 100%;
				height: 1rpx;
				background: #E6E6E6;
				margin: 27rpx 0;
			}

			.item {
				@include flexX;
				justify-content: space-between;

				text {
					@include fontStyle(30rpx, 400, #919191, 42rpx);
				}
			}
		}

		.footer {
			position: fixed;
			bottom: 0;
			background: #ffffff;
			height: 120rpx;
			width: 100%;
			@include flexX;
			flex-direction: row-reverse;
			align-items: center;
			padding: 0 40rpx;
			box-sizing: border-box;

			.btn {

				text {
					@include fontStyle(32rpx, 500, #ffffff, 45rpx);
					background: #FD5134;
					padding: 11rpx 35rpx;
					border-radius: 35rpx;
					border: 1rpx solid #FD5134;
				}
			}
		}
	}
</style>