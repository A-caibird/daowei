<template>
	<view class="container">
		<view class="nav">
			<text>
				实名认证
			</text>
			<image @tap="back" class="back" src="@/static/whiteLeft.png">
			</image>
		</view>
		<view class="empty">
		</view>
		<view class="part1">
			<view class="title">
				<text>上传证件照</text>
			</view>
			<view class="file">
				<view class="one">
					<image src="@/static/zheng.png">

					</image>

					<text>
						身份证正面
					</text>
				</view>
				<view class="one">
					<image src="@/static/face.png">

					</image>

					<text>
						人脸照
					</text>
				</view>
			</view>



		</view>
		<view class="part2">
			<view class="one">
				<text>
					姓名
				</text>
				<input placeholder="例如：张三" placeholder-class="pla" style="width:160rpx" />
			</view>
			<view class="one">
				<text>
					身份证号
				</text>
				<input style="width:260rpx" />
			</view>
		</view>
		<view class="part3">
			<view class="protocol">
				<view class="select">
					<image src="@/static/selected.png" v-if="ok" @tap="ok=false">
					</image>
					<image src="@/static/notSelect.png" v-if="!ok" @tap="ok=true">
					</image>
				</view>
				<view class="text-desc">
					<text>
						确认已阅读并同意
					</text>
					<text>
						《用户使用条例》
					</text>

					<text>
						《隐私保护政策》
					</text>
					<text>
						授权我们查询您的身份信息及面部信息。
					</text>
				</view>
			</view>
			<view class="btn">
				<text>
					登录
				</text>
			</view>
		</view>
	</view>

</template>

<script>
	export default {
		data() {
			return {
				ok: true
			}
		},
		methods: {
			back() {
				uni.navigateBack();
			}
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
			position: fixed;
			left: 0rpx;
			top: 0rpx;
			z-index: 1;

			text {
				@include fontStyle(36rpx, 700, #ffffff, 36rpx);
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

		.part1 {
			padding: 40rpx;
			box-sizing: border-box;
			background: #ffffff;
			margin-top: 20rpx;

			.title {
				text {
					@include fontStyle(36rpx, 700, #2E2727, 36rpx);
				}
			}

			.file {
				width: 100%;
				padding: 0 22rpx;
				margin-top: 37rpx;
				@include flexX;
				align-items: center;
				justify-content: space-between;

				.one {
					@include flexY;
					align-items: center;

					image {
						width: 299rpx;
						height: 191rpx;
						margin-bottom: 28rpx;
					}

					text {
						@include fontStyle(24rpx, 400, #CACDD1, 33rpx);
					}
				}
			}
		}

		.part2 {
			background: #ffffff;
			margin-top: 20rpx;

			.one {
				@include flexX;
				align-items: center;
				justify-content: space-between;
				padding: 40rpx;
				box-sizing: border-box;

				text {
					@include fontStyle(32rpx, 700, #2E2727, 45rpx);
				}

				.pla {
					@include fontStyle(32rpx, 400, #B5B5B5, 45rpx);
				}
			}
		}

		.part3 {

			.protocol {
				width: 100%;
				padding: 0 38rpx;

				margin-bottom: 48rpx;
				margin-top: 134rpx;
				@include flexX;
				align-items: center;

				.select {
					image {
						width: 40rpx;
						height: 40rpx;
					}
				}

				.text-desc {
					margin-left: 15rpx;
					width: 600rpx;

					text {
						@include fontStyle(22rpx, 400, #757A85, 30rpx);

						&:nth-of-type(2) {
							color: #E94A44;
						}

						&:nth-of-type(3) {
							color: #E94A44;
						}
					}
				}
			}

			.btn {
				width: 560rpx;
				height: 98rpx;
				text-align: center;
				@include flexY;
				justify-content: center;
				align-items: center;
				background: #E94A44;
				border-radius: 57rpx;
				position: relative;
				left: 50%;
				transform: translateX(-50%);


				text {
					@include fontStyle(36rpx, 500, #ffffff, 50rpx);
					letter-spacing: 2px;
				}
			}
		}
	}
</style>