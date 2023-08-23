<template>
	<view class="container" :class="{active:(quit|logOut)}">
		<view class="nav">
			<text>
				设置
			</text>
			<image @tap="uni.navigateBack()" class="back" src="@/static/whiteLeft.png">
			</image>
		</view>
		<view class="empty">
		</view>
		<view class="option">
			<view class="one" @tap="op(1)">
				<text>
					推出账号
				</text>
				<image src="@/static/whiteRight.png">

				</image>
			</view>
			<view class="divi"></view>
			<view class="one" @tap="op(2)">
				<text>
					注销账户
				</text>
				<image src="@/static/whiteRight.png">

				</image>
			</view>
		</view>
		<template v-if="quit">
			<pop v-model:show="quit">
				<template #title>
					<text>
						退出登陆
					</text>
				</template>
				<template #desc>
					<text>
						退出登录后需重新登录，才能查看信息，确认是否退出登录
					</text>
				</template>
			</pop>
		</template>
		<template v-if="logOut">
			<pop v-model:show="logOut">
				<template #title>
					<text>
						注销账户
					</text>
				</template>
				<template #desc>
					<text>
						注销账户后，您的信息也将被删除，确认是否注销账户
					</text>
				</template>
			</pop>
		</template>
	</view>
</template>

<script>
	import pop from "@/components/quitPop.vue"
	export default {
		components: {
			pop
		},
		data() {
			return {
				quit: false,
				logOut: false,

			}
		},
		methods: {
			op(num) {
				if (num == 1) {
					this.quit = true
				} else this.logOut = true
			}
		}
	}
</script>

<style lang="scss" scoped>
	.container {
		@include full-screen-color;
		background-color: #F8F8F8;
		overflow-y: auto;

		&.active {
			&::after {
				content: '';
				position: absolute;
				top: 0;
				bottom: 0;
				right: 0;
				left: 0;
				background: #000000;
				opacity: 0.5;
				z-index: 2;
			}
		}

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


		.option {
			background: #ffffff;
			padding: 27rpx 33rpx;
			box-sizing: border-box;
			margin-top: 20rpx;

			.divi {
				height: 1rpx;
				background: #EAEAEA;
				width: 100%;
				margin: 28rpx 0;
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