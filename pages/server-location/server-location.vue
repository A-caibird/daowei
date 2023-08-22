<template>
	<view class="container">
		<view class="nav">
			<text>
				服务地点
			</text>
			<image @tap="uni.navigateBack()" class="back" src="@/static/whiteLeft.png">
			</image>
			<text>
				保存
			</text>
		</view>
		<view class="empty">
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
		
				&:last-of-type {
					position: absolute;
					right: 32rpx;
					bottom: 20rpx;
					margin: 0;
				}
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
	}
</style>