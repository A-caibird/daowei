<template>
	<view class="container">
		<view class="title">
			<text>
				登录
			</text>
		</view>
		<view class="image-box">
			<image src="@/static/login.png">

			</image>
		</view>
		<view class="form">
			<view class="one">
				<view class="title">
					<text>
						手机号
					</text>
				</view>
				<view class="input-box">
					<input placeholder="请输入您的手机号" placeholder-class="pla" />
				</view>
				<view class="divi"></view>
			</view>
			<view class="one">
				<view class="title">
					<text>
						验证码
					</text>
				</view>
				<view class="input-box">
					<input placeholder="请输入验证码" placeholder-class="pla" />
					<view class="btn">
						<text>
							获取验证码
						</text>
					</view>
				</view>
			</view>
		</view>
		<view class="btn" @tap="logIn">
			<text>
				登录
			</text>
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
			logIn(){
				uni.navigateTo({
					url: '/pages/mine/mine',
				});
			}
		}
	}
</script>

<style lang="scss">
	.container {
		@include full-screen-color;
		background: #FFFFFF;
		overflow-y: auto;

		&>.title {
			margin-top: 128rpx;
			width: 100%;
			@include flexY;
			align-items: center;

			text {
				@include fontStyle(36rpx, 700, #333333, 36rpx);
			}
		}

		.image-box {
			width: 100%;
			@include flexY;
			align-items: center;
			margin-top: 74rpx;

			image {

				width: 435rpx;
				height: 307rpx;
			}
		}

		.form {
			margin-top: 60rpx;
			box-sizing: border-box;
			padding: 0 48rpx;

			.one {
				&:last-of-type {
					margin-top: 32rpx;
				}

				.title {
					margin-bottom: 16rpx;

					text {
						@include fontStyle(36rpx, 700, #333333, 36rpx);
					}
				}

				.input-box {
					box-sizing: border-box;
					padding: 28rpx 0;
					@include flexX;
					justify-content: space-between;
					width: 100%;
					box-shadow: 0rpx 1rpx 0rpx 0rpx #E8E8E8;

					.pla {
						@include fontStyle(32rpx, 400, #DDDDDD, 45rpx);
					}

					.btn {
						text {
							@include fontStyle(32rpx, 400, #ffffff, 32rpx);
							background: #FB862D;
							border-radius: 32rpx;
							padding: 9rpx 20rpx;
							padding-top:5rpx;
						}
					}


				}

				.divi {
					margin-top: 18rpx;
				}
			}
		}

		&>.btn {
			margin: 95rpx;
			margin-bottom: 0rpx;
			width: 560rpx;
			text-align: center;

			text {
				@include fontStyle(36rpx, 500, #ffffff, 50rpx);
				letter-spacing: 2px;
				background: #E94A44;
				border-radius: 57rpx;
				display: block;
				padding:24rpx 0;
			}
		}
	}
</style>