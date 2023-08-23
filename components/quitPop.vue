<template>
	<view class="pop">
		<view class="title">
			<slot name="title"></slot>
		</view>
		<view class="desc">
			<slot name="desc"></slot>
		</view>

		<view class="btns">
			<view class="b1" @tap="op(1)">
				<text>
					取消
				</text>
			</view>
			<view class="b2" @tap="op(2)">
				<text>
					确认
				</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		model: {
			prop: 'show',
			event: 'close'
		},
		props: {
			show: [Boolean]
		},
		data() {
			return {}
		},
		methods: {
			op(num) {
				if (num == 1) {
					this.$emit('close', false);
				} else if (num == 2){
					uni.navigateTo({
						url:'/pages/logIn/logIn'
					})
				}
			}
		}
	}
</script>

<style lang="scss" scoped>
	.pop {
		position: fixed;
		top: 50%;
		left: 50%;
		transform: translate3d(-50%, -50%, 0);
		width: 540rpx;
		background: #FFFFFF;
		border-radius: 10rpx;
		z-index: 100;

		.title {
			@include flexY;
			align-items: center;
			margin-top: 56rpx;
			margin-bottom: 18rpx;


			text {
				@include fontStyle(36rpx, 400, #000000, 36rpx);
			}
		}

		.desc {
			padding: 0 42rpx;
			box-sizing: border-box;
			width: 100%;
			text-align: center;

			text {
				@include fontStyle(30rpx, 400, #888888, 45rpx);
				white-space: pre-wrap;
			}
		}

		.btns {
			border-top: 1rpx solid #dddddd;
			@include flexX;
			justify-content: space-between;
			margin-top: 33rpx;

			.b1 {
				@include flexY;
				justify-content: center;
				align-items: center;
				border-right: 1rpx solid #dddddd;
				width: 100%;
				height: 100%;

				text {
					margin: 32rpx 0;
					@include fontStyle(36rpx, 400, #333333, 36rpx);
				}

			}

			.b2 {
				@extend .b1;
				border: none;

				text {
					color: #EB5B58;
				}
			}
		}
	}
</style>