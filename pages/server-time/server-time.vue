<template>
	<view class="container">
		<view class="nav">
			<text>
				服务时间
			</text>
			<image @tap="uni.navigateBack()" class="back" src="@/static/whiteLeft.png">
			</image>
		</view>
		<view class="empty">
		</view>
		<view class="week">
			<view class="title">
				<view class="left">

				</view>
				<view class="right">
					<text>
						选择星期
					</text>
				</view>
			</view>
			<view class="divi">

			</view>
			<view class="area">
				<view class="one-week" v-for="(item,index) of week" :key="index" @tap="selectWeek(index)">
					<text :class="{active:item.ok}">
						{{item.time}}
					</text>
				</view>
			</view>
		</view>

		<view class="time">
			<view class="title">
				<view class="left">
					<view class="icon">

					</view>
					<view class="text-desc">
						<text>
							选择时间段
						</text>
					</view>
				</view>
				<view class="right">
					<text>
						{{timeStart}}:00-{{timeEnd}}:00
					</text>
				</view>
			</view>
			<view class="divi">
			</view>
			<view class="area">
				<view class="oneline" v-for="item1 of 5" :key="item1">
					<view class="one-time" v-for="item2 of 4" :key="item2" @tap="timeSelect((4*item1+item2))"
						:class="{active:selected((4*item1+item2))}">
						<text>
							{{(4*item1+item2)>=10?(4*item1+item2):('0'+(4*item1+item2))}}:00
						</text>
					</view>
				</view>
			</view>
		</view>
		<view class="btn">
			<text>
				保存
			</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				week: [{
						time: '周一',
						ok: false,
					},
					{
						time: '周二',
						ok: false,
					},
					{
						time: '周三',
						ok: false,
					},
					{
						time: '周四',
						ok: false,
					},
					{
						time: '周五',
						ok: false,
					},
					{
						time: '周六',
						ok: false,
					},
					{
						time: '周日',
						ok: false,
					},
				],
				selectedTime: [8,20],
			}
		},
		computed: {
			timeStart() {
				if (this.selectedTime.length < 2) return '00'
				let a = this.selectedTime[0] < this.selectedTime[1] ? this.selectedTime[0] : this.selectedTime[1]
				return a > 10 ? a : (a + '0');
			},
			timeEnd() {
				if (this.selectedTime.length < 2) return '00'
				let a = this.selectedTime[0] > this.selectedTime[1] ? this.selectedTime[0] : this.selectedTime[1]
				return a > 10 ? a : (a + '0')
			}
		},
		methods: {
			timeSelect(num) {
				let newarr = [];
				if (this.selectedTime.includes(num)) {
					newarr = this.selectedTime.filter(item => {
						item !== num
					});
					this.selectedTime = newarr;
				} else {
					if (this.selectedTime.length < 2) {} else if (this.selectedTime.length) {
						this.selectedTime.splice(this.selectedTime.length - 1, 1);
					}
					this.selectedTime.push(num)
				}
			},
			selected(num) {
				return this.selectedTime.includes(num);
			},
			selectWeek(num) {
				this.week = this.week.map(function(item, index) {
					let ok1 = item.ok;
					if (num == index) {
						ok1 = !item.ok
					}
					return {
						time: item.time,
						ok: ok1
					}
				})
			}
		},
		mounted() {

		}
	}
</script>

<style lang="scss" scoped>
	.container {
		@include full-screen-color;
		background-color: #F8F8F8;
		overflow-y: auto;
		padding-bottom: 400rpx; //增大离手机底部的距离


		.nav {
			width: 100%;
			height: 128rpx;
			background: #E94A44;
			@include flexY;
			flex-direction: column-reverse;
			align-items: center;
			justify-self: flex-end;
			position: fixed;
			left: 0rpx;
			top: 0rpx;
			z-index: 1;

			text {
				@include fontStyle(36rpx, 500, #ffffff, 36rpx);
				margin-bottom: 20rpx;
			}

			.back {
				width: 32rpx;
				height: 32rpx;
				position: absolute;
				left: 32rpx;
				bottom: 20rpx;
			}
		}

		.empty {
			width: 100%;
			height: 128rpx;
		}

		@mixin part {
			padding: 28rpx 40rpx;
			background: #ffffff;
			box-sizing: border-box;
			margin-top: 20rpx;
		}

		.week {
			@include part;

			.title {
				@include flexX;
				align-items: center;

				.left {
					border-radius: 50%;
					background-color: #E94A44;
					width: 12rpx;
					height: 12rpx;
					margin-right: 10rpx;
				}

				.right {
					text {
						@include fontStyle(32rpx, 500, #2E2727, 45rpx);
					}
				}
			}

			.divi {
				width: 100%;
				height: 1rpx;
				background: #EAEAEA;
				margin-top: 28rpx;
				margin-bottom: 16rpx;
			}

			.area {
				@include flexX;
				gap: 20rpx;
				flex-wrap: wrap;

				.one-week {
					margin-top: 20rpx;

					text {
						@include fontStyle(28rpx, 500, #ffffff, 40rpx);
						background: #F8F8F8;
						border-radius: 30rpx;
						padding: 10rpx 40rpx;

						&.active {
							background: #E94A44;
						}
					}
				}
			}
		}

		.time {
			@include part;

			.title {
				@include flexX;
				align-items: center;
				justify-content: space-between;

				.left {
					@include flexX;
					align-items: center;

					.icon {
						border-radius: 50%;
						background-color: #E94A44;
						width: 12rpx;
						height: 12rpx;
						margin-right: 10rpx;
					}

					.text-desc {
						text {
							@include fontStyle(32rpx, 500, #2E2727, 45rpx);
						}
					}
				}

				.right {
					text {
						@include fontStyle(32rpx, 400, #2E2727, 45rpx);
					}
				}
			}


			.divi {
				width: 100%;
				height: 1rpx;
				background: #EAEAEA;
				margin-top: 28rpx;
				margin-bottom: 16rpx;
			}

			.area {
				@include flexY;

				.oneline {
					@include flexX;
					justify-content: space-between;
					margin-top: 20rpx;
					background: #F8F8F8;

					.one-time {
						text {
							@include fontStyle(32rpx, 400, #2E2727, 45rpx);
							padding: 0rpx 15rpx;
							padding-bottom: 2rpx;
						}

						&.active {
							text {
								color: #ffffff;
								background-color: #E94A44;
								border-radius: 24rpx;
							}
						}
					}

					&:nth-of-type(1) {
						background: transparent;

						.one-time {
							text {
								@include fontStyle(32rpx, 400, #B5B5B5, 45rpx);
								padding: 0rpx 15rpx;
								padding-bottom: 2rpx;
							}

							&.active {
								text {
									color: #ffffff;
									background-color: #E94A44;
									position: relative;
									border-radius: 24rpx;
								}
							}
						}
					}

					&:nth-of-type(5) {
						background: transparent;

						.one-time {
							text {
								@include fontStyle(32rpx, 400, #B5B5B5, 45rpx);
								padding: 0rpx 15rpx;
								padding-bottom: 3rpx;
							}

							&.active {
								text {
									color: #ffffff;
									background-color: #E94A44;
									position: relative;
									border-radius: 24rpx;
								}
							}
						}
					}
				}
			}
		}

		.btn {
			width: 100%;
			@include flexY;
			position: absolute;
			bottom: 75rpx;

			text {
				align-self: center;
				@include fontStyle(36rpx, 500, #ffffff, 45rpx);
				letter-spacing: 2rpx;
				background-color: #E94A44;
				padding: 20rpx 200rpx;
				border-radius: 57rpx;
			}
		}
	}
</style>