<template>
	<view class="container">
		<view class="nav">
			<text>个人信息</text>
			<image @tap="back" class="back" src="@/static/whiteLeft.png">

			</image>
		</view>
		<view class="avatar">
			<view class="left">
				<text>头像</text>
			</view>
			<view class="right">
				<image>

				</image>

				<image>
				</image>
			</view>
		</view>
		<view class="phone">
			<view class="fir">
				<view class="left">
					<text>
						实名认证
					</text>
				</view>
				<view class="right">
					<text>已认证</text>
					<image src="@/static/whiteRight.png">
					</image>
				</view>
			</view>
			<view class="divi">

			</view>
			<view class="fir">
				<view class="left">
					<text>
						手机号
					</text>
				</view>
				<view class="right">
					<text>168769098</text>
					<image src="@/static/whiteRight.png">
					</image>
				</view>
			</view>
		</view>
		<view class="other">
			<view class="fir">
				<view class="left">
					<text>
						上传资质
					</text>
				</view>
				<view class="right">
					<text>爱吃鱼的喵</text>
					<image src="@/static/whiteRight.png">
					</image>
				</view>
			</view>
			<view class="divi"></view>
			<view class="fir">
				<view class="left">
					<text>
						职称
					</text>
				</view>
				<view class="right">
					<text>专业修理一级</text>
					<image src="@/static/whiteRight.png">
					</image>
				</view>
			</view>
			<view class="divi"></view>
			<view class="fir">
				<view class="left">
					<text>
						职业技能
					</text>
				</view>
				<view class="right">
					<text>专业修理</text>
					<image src="@/static/whiteRight.png">
					</image>
				</view>
			</view>
		</view>
		<view class="text-area">
			<view class="title">
				<text>
					个人简历
				</text>
			</view>
			<view>
				<textarea placeholder="请输入您的简历" placeholder-class="placeholder-class"></textarea>
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

		.nav {
			width: 100%;
			height: 128rpx;
			background: #E94A44;
			@include flexY;
			flex-direction: column-reverse;
			align-items: center;
			justify-self: flex-end;
			position: relative;

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

		@mixin part {
			padding: 32rpx 40rpx;
			box-sizing: border-box;
			background: #ffffff;
		}

		.avatar {
			@include flexX;
			@include part;
			margin-top: 20rpx;
			justify-content: space-between;
			align-items: center;

			.left {
				text {
					@include fontStyle(32rpx, 400, #2E2727, 45rpx);
				}
			}

			.right {
				@include flexX;
				align-items: center;

				image {
					&:first-of-type {
						border-radius: 50%;
						width: 90rpx;
						height: 90rpx;
						margin-right: 10rpx;
						background-color: red;
					}

					&:last-of-type {
						width: 24rpx;
						height: 24rpx;
						background-color: red;
					}
				}
			}
		}

		.phone {
			@include part;
			margin-top: 20rpx;

			.fir {
				@include flexX;
				align-items: center;
				justify-content: space-between;

				.left {
					text {
						@include fontStyle(32rpx, 400, #2E2727, 45rpx);
					}
				}

				.right {
					@include flexX;
					align-items: center;

					text {
						@include fontStyle(32rpx, 400, #2E2727, 45rpx);
					}

					image {
						width: 24rpx;
						height: 24rpx;
						background-color: red;
					}
				}
			}

			.divi {
				width: 100%;
				height: 1rpx;
				background: #EAEAEA;
				margin: 33rpx 0;
			}
		}

		.other {
			@extend .phone;
		}

		.text-area {
			@include part;
			margin-top: 20rpx;

			.title {
				margin-bottom: 40rpx;

				text {
					@include fontStyle(32rpx, 400, #2E2727, 45rpx);
				}
			}

			.placeholder-class {
				@include fontStyle(32rpx, 400, #DDDDDD, 45rpx);
			}
		}
	}
</style>