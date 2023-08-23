<template>
	<view class="container">
		<view class="nav">
			<text>
				意见反馈
			</text>
			<image @tap="uni.navigateBack()" class="back" src="@/static/whiteLeft.png">
			</image>
		</view>
		<view class="empty">
		</view>
		<view class="feed">
			<textarea placeholder="你可以在这里吐槽，提意见" placeholder-class="pla" style="height:402rpx;" />
		</view>
		<view class="btn">
			<text>
				提交
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

		.feed {
			box-sizing: border-box;
			margin-top: 20rpx;
			padding: 40rpx;
			background: #ffffff;

			.pla {
				@include fontStyle(32rpx, 400, #DDDDDD, 45rpx);
			}
			
		}
		.btn{
			width: 100%;
			@include flexY;
			align-items: center;
			margin-top: 68rpx;
			text{
				@include fontStyle(36rpx, 500, #ffffff,50rpx);
				padding:24rpx 242rpx;
				background: #E94A44;
				border-radius: 57rpx;
			}
		}
	}
</style>