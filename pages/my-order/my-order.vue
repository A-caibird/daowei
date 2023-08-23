<template>
	<view class="container">
		<view class="content-box">
			<view class="nav">
				<view class="left">
				</view>
				<view class="center">
					<text>
						订单
					</text>
				</view>
				<view class="right">
					<image src="@/static/share.png">
					</image>
					<text>
						分享
					</text>
				</view>

			</view>
			<view class="avatar-area">
				<view class="left">
					<image src="@/static/avatar.png">

					</image>
				</view>
				<view class="right">
					<view class="up">
						<text>张三</text>
						<image src="@/static/greyRight.png"></image>
					</view>
					<view class="down">

						<image></image>
						<text>维修中心</text>
					</view>
				</view>
			</view>
			<view class="text-desc">
				<text>
					5年技师经验，擅长维修各个家电类型，洗衣机，空调，电视，冰箱，热水器，油烟机等等
				</text>
			</view>
			<view class="select-area">
				<view class="item" @tap="select(0)" :class="{active:selectList[0]}">
					<text>
						新订单
					</text>
					<image src="../../static/selectedBackground.png">

					</image>
				</view>
				<view class="item" @tap="select(1)" :class="{active:selectList[1]}">
					<text>
						进行中
					</text>
					<image src="../../static/selectedBackground.png">

					</image>
				</view>
				<view class="item" @tap="select(2)" :class="{active:selectList[2]}">
					<text>
						已完成
					</text>
					<image src="../../static/selectedBackground.png">

					</image>
				</view>
				<view class="item" @tap="select(3)" :class="{active:selectList[3]}">
					<text>
						全部
					</text>
					<image src="../../static/selectedBackground.png">

					</image>
				</view>
			</view>
			<view class="order-area">
				<view class="order-item" :class="{fir:!index}" v-for="(item,index) of 2" :key="index"
					@tap="goTo('待确认')">
					<view class="order-code">
						<view class="left">
							<text>
								订单编号：
							</text>
							<text>
								210990343490809
							</text>
						</view>
						<view class="right">

							<text>
								待确认
							</text>
						</view>

					</view>
					<view class="divi">
					</view>
					<view class="time">
						<text>预约时间：</text>
						<text>2021-01-03</text>
						<text>（周日）</text>
						<text>19:00</text>
					</view>
					<view class="person">
						<text>预 约 人： </text>
						<text>张三</text>
						<text>13809090090</text>

					</view>
					<view class="adress">
						<text>预约地址： </text>
						<text>宁波鄞州区南峪校区二期恒业大厦3幢10 </text>
					</view>
					<view class="divi">
					</view>
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
								×3
							</text>
						</view>
					</view>
					<view class="divi">
					</view>
					<view class="btn">
						<text>
							确认
						</text>
					</view>
				</view>
			</view>
		</view>
		<my-footer :cur="0"></my-footer>
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
				selectList: [false, false, false, true]
			}
		},
		methods: {
			select(num) {
				this.selectList = this.selectList.map(function(item, index) {
					return index == num
				})
				console.log(this.selectList)
			},
			goTo(str) {
				if (str == '待确认') {
					uni.navigateTo({
						url: '/pages/order-detail/order-detail'
					})
				}
			}
		}
	}
</script>

<style lang="scss" scoped>
	.container {
		@include full-screen-color;
		background-color: #F8F8F8;
		overflow-y: auto;

		&::after {
			content: '';
			position: absolute;
			top: 0;
			left: 0;
			background-image: url('@/static/background.png');
			width: 100%;
			height: 622rpx;
		}

		.content-box {
			width: 100%;
			z-index: 1;
			position: absolute;
			top: 100rpx;
			box-sizing: border-box;
			padding-bottom: 400rpx;

			.nav {
				@include flexX;
				width: 100%;
				justify-content: space-between;
				padding: 0 68rpx;
				box-sizing: border-box;

				.left {
					width: 84rpx;
					height: 34rpx;
				}

				.center {
					text {
						@include fontStyle(36rpx, 700, #Ffffff, 36rpx);
					}
				}

				.right {
					@include flexX;
					place-items: center;
					gap: 0 20rpx;

					text {
						@include fontStyle(28rpx, 400, #Ffffff, 34rpx);
					}

					image {
						width: 34rpx;
						height: 34rpx;
					}
				}

			}

			.avatar-area {
				@include flexX;
				place-items: center;
				gap: 0 20rpx;
				margin-top: 87rpx;
				padding: 0 68rpx;

				.left {
					image {
						width: 120rpx;
						height: 120rpx;
						border-radius: 50%;
					}
				}

				.right {

					.up {
						@include flexX;
						gap: 0 20rpx;

						text {
							@include fontStyle(36rpx, 500, #Ffffff, 50rpx);
						}

						image {
							width: 11rpx;
							height: 20rpx;
							position: relative;
							top: 12rpx;
						}
					}

					.down {
						@include flexX;
						gap: 0 10rpx;
						place-items: center;

						text {
							@include fontStyle(28rpx, 400, #Ffffff, 40rpx);
						}

						image {
							width: 26rpx;
							height: 26rpx;
							background: #F8F8F8;
						}
					}
				}
			}


			.text-desc {
				padding: 0 68rpx;

				text {

					@include fontStyle(22rpx, 400, #Ffffff, 27rpx);
				}
			}

			.select-area {
				@include flexX;
				justify-content: space-between;
				margin-top: 73rpx;
				padding: 0 68rpx;

				.item {
					@include flexY;
					place-items: center;
					gap: 29rpx 0;

					text {
						@include fontStyle(28rpx, 400, #dcdcdc, 40rpx);
					}

					image {
						width: 80rpx;
						height: 9rpx;
						visibility: hidden;
					}

					&.active {
						text {
							@include fontStyle(28rpx, 400, #ffffff, 40rpx);
						}

						image {
							visibility: visible;
						}
					}
				}
			}

			.order-area {
				width: 100%;
				box-sizing: border-box;
				@include flexY;
				gap: 25rpx;

				.order-item {
					width: 100%;
					padding: 27rpx 46rpx;
					background-color: #ffffff;
					position: relative;
					box-sizing: border-box;
					@include flexY;

					&.fir {
						border-radius: 40rpx 40rpx 0rpx 0rpx;
					}

					.order-code {
						@include flexX;
						justify-content: space-between;

						.left {
							@include fontStyle(24rpx, 400, #919191, 33rpx);
						}

						.right {
							text {
								@include fontStyle(26rpx, 400, #E94A44, 37rpx);
							}

						}
					}

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
								@include fontStyle(28rpx, 400, #919191, 40rpx);
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
								@include fontStyle(28rpx, 400, #919191, 40rpx);
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
								@include fontStyle(28rpx, 400, #919191, 40rpx);
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

					.content-info {
						@include flexX;
						position: relative;
						justify-content: space-between;

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
									@include fontStyle(28rpx, 400, #919191, 33rpx);
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

					.btn {
						align-self: flex-end;

						text {
							background: #E94A44;
							border-radius: 26rpx;
							padding: 10rpx 36rpx;
							box-sizing: border-box;
							@include fontStyle(24rpx, 400, #ffffff, 33rpx);
						}
					}
				}
			}
		}
	}
</style>