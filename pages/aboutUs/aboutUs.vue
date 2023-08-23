<template>
	<view class="container">
		<view class="nav">
			<text>
				关于我们
			</text>
			<image @tap="uni.navigateBack()" class="back" src="@/static/whiteLeft.png">
			</image>
		</view>
		<view class="empty">
		</view>
		<view class="softInfo">
			<view class="image-box">
				<image src="@/static/logo.png">

				</image>
			</view>
			<view class="name">
				<text>
					到位
				</text>
			</view>
			<view class="version">
				<text>
					版本号：1.1.0
				</text>
			</view>
			<view class="desc">
				<text>
					到位技师端是专门为技师接单而设计的，提交实名认证后，就可以轻松接单
				</text>
			</view>
		</view>
		<view class="protocol">
			<view class="one">
				<text>
					服务协议
				</text>
				<image src="@/static/whiteRight.png">

				</image>
			</view>
			<view class="divi"></view>
			<view class="one">
				<text>
					隐私协议
				</text>
				<image src="@/static/whiteRight.png">
			
				</image>
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

		.softInfo {
			padding: 0 92rpx;
			padding-top: 138rpx;
			background: #ffffff;
			box-sizing: border-box;
			@include flexY;
			align-items: center;

			.image-box {
				width: 120rpx;
				height: 120rpx;

				image {
					width: 120rpx;
					height: 120rpx;
				}
			}

			.name {
				margin-top: 28rpx;

				text {
					@include fontStyle(32rpx, 700, #454545, 45rpx);
				}
			}

			.version {
				margin-top: 14rpx;

				text {
					@include fontStyle(32rpx, 400, #696565, 45rpx);
				}
			}

			.desc {
				width: 100%;
				text-align: center;
				margin-top: 27rpx;
				margin-bottom: 57rpx;

				text {
					@include fontStyle(24rpx, 400, #696565, 33rpx);
					white-space: pre-wrap;

				}
			}
		}

		.protocol {
			background: #ffffff;
			box-sizing: border-box;
			padding: 27rpx 33rpx;
			margin-top: 20rpx;
			.divi{
				height: 1rpx;
				background: #EAEAEA;
				width: 100%;
				margin:28rpx 0;
			}
			.one {
				@include flexX;
				align-items: center;
				justify-content: space-between;

				text {
					@include fontStyle(32rpx, 400, #454545, 45rpx);
				}

				image {
					background-color: red;
					width: 24rpx;
					height: 24rpx;
				}
			}
		}
	}
</style>