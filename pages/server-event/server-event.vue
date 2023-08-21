<template>
	<view class="container">
		<view class="nav">
			<text>
				服务项目
			</text>
			<image @tap="uni.navigateBack()" class="back" src="@/static/whiteLeft.png">
			</image>
			<text>
				保存
			</text>
		</view>
		<view class="empty">
		</view>
		<!-- 占个位置,让下面的元素下面一点去 -->
		<view class="selected">
			<view class="title">
				<view class="left">

				</view>
				<view class="right">
					<text>
						已选择项目
					</text>
				</view>
			</view>
			<view class="area">
				<view class="one" v-for="(item,index) of selected" :key="index">
					<text>
						{{item.name}}
					</text>
					<view class="icon" @tap="cancelSelect(item.kind,item.__index)">
						<u-icon name="close" color="#F8F8F8" size="15rpx"></u-icon>
					</view>
				</view>
			</view>
		</view>
		<view class="select-title">
			<view class="left">

			</view>
			<view class="right">
				<text>
					选择项目
				</text>
			</view>
		</view>
		<view class="select-area">
			<u-collapse :border="true">
				<u-collapse-item title="上门维修" name="Docs guide" :border="true">
					<view class="event-area">
						<view class="one" @tap="" v-for="(item,index) of selectOption['上门维修'] " :key="index"
							@tap="select('上门维修',index)" :class="{active:item.ed}">
							<text>{{item.name}}</text>
						</view>
					</view>
				</u-collapse-item>
				<u-collapse-item title="家庭保洁" name="Docs guide" :border="true">
					<view class="event-area">
						<view class="one" v-for="item of 10" :key="item">
							<text>空调维修</text>
						</view>

					</view>
				</u-collapse-item>
				<u-collapse-item title="搬家拉货" name="Docs guide" :border="true">
					<view class="event-area">
						<view class="one" v-for="item of 10" :key="item">
							<text>空调维修</text>
						</view>

					</view>
				</u-collapse-item>
				<u-collapse-item title="上门安装" name="Docs guide" :border="true">
					<view class="event-area">
						<view class="one" v-for="item of 10" :key="item">
							<text>空调维修</text>
						</view>

					</view>
				</u-collapse-item>
				<u-collapse-item title="保姆月嫂" name="Docs guide" :border="true">
					<view class="event-area">
						<view class="one" v-for="item of 10" :key="item">
							<text>空调维修</text>
						</view>

					</view>
				</u-collapse-item>
				<u-collapse-item title="经典门票" name="Docs guide" :border="true">
					<view class="event-area">
						<view class="one" v-for="item of 10" :key="item">
							<text>空调维修</text>
						</view>

					</view>
				</u-collapse-item>
				<u-collapse-item title="餐饮购券" name="Docs guide" :border="true">
					<view class="event-area">
						<view class="one" v-for="item of 10" :key="item">
							<text>空调维修</text>
						</view>

					</view>
				</u-collapse-item>
			</u-collapse>
		</view>
		<view class="btn" :class="{active:have}">
			<text>
				确定
			</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				selectOption: {
					"上门维修": [{
							name: "家电维修",
							ed: false
						},
						{
							name: "热水器维修",
							ed: false
						},
					]
				}
			}
		},
		computed: {
			have() {
				for (let a in this.selectOption) {
					for (let b of this.selectOption[a]) {
						if (b.ed) return true;
					}
				}
				return false;
			},
			selected() {
				let arr = [];
				for (let a in this.selectOption) {
					for (let [index, b] of this.selectOption[a].entries()) {
						if (b.ed) {
							let val = {
								kind: a,
								__index: index,
								name: b.name
							}
							arr.push(val)
						}
					}
				}
				return arr;
			}
		},
		methods: {
			select(str, index) {
				console.log(str, index, this.selectOption[str]);

				this.selectOption[str] = this.selectOption[str].map(function(item, index1) {
					let newed = item.ed;
					if (index == index1) {
						newed = !item.ed;
					}
					let val = {
						name: item.name,
						ed: newed
					};
					return val;
				})
				// console.log(this.selectOption)
			},
			cancelSelect(str, __index){
				this.selectOption[str] = this.selectOption[str].map(function(item, index1) {
					let newed = item.ed;
					if (index1 == __index) {
						newed = false;
					}
					let val = {
						name: item.name,
						ed: newed
					};
					return val;
				})
			}
		},
		created() {}
	}
</script>

<style lang="scss" scoped>
	::v-deep .u-cell {
		padding-left: 40rpx;
		padding-right: 30rpx;

	}

	::v-deep .u-collapse {
		background-color: #F8F8F8;

		&>* {
			margin-top: 20rpx;
		}

		&:first-child {
			margin-top: 0 !important;
		}
	}

	::v-deep .u-collapse-item {
		background-color: #ffffff;
	}

	::v-deep .u-line {
		border: none !important;
	}

	::v-deep .u-line {
		border: none !important;
	}

	::v-deep .u-line[data-v-e7ce28f2] {
		border: none !important;
	}

	::v-deep .u-line {
		border-bottom: 1rpx solid #EAEAEA !important;
	}

	::v-deep .u-cell__body[data-v-913eaa32] {
		padding: 30rpx 0;
		padding-left: 20rpx;
		padding-right: 0;

	}


	::v-deep .u-collapse-item__content__text[data-v-3bf52cdf] {
		padding-left: 0;
		padding-right: 0;
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

		@mixin part {
			padding: 32rpx 40rpx;
			box-sizing: border-box;
			background: #ffffff;
		}

		.selected {
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
						@include fontStyle(32rpx, 700, #2E2727, 45rpx);
					}
				}
			}

			.area {
				padding-left: 20rpx;
				@include flexX;
				flex-wrap: wrap;
				gap: 20rpx;
				margin-top: 42rpx;



				.one {
					border-radius: 30rpx;
					border: 2rpx solid #E94A44;
					padding: 5rpx 20rpx;
					@include flexX;
					align-items: center;
					box-sizing: border-box;

					text {
						@include fontStyle(28rpx, 400, #E94A44, 40rpx);
						display: inline-block;
					}

					.icon {
						background-color: #E94A44;
						border-radius: 50%;
						display: inline-block;
						margin-left: 5rpx;
						padding: 5rpx;
						box-sizing: border-box;
					}
				}
			}
		}

		.select-title {
			@include flexX;
			align-items: center;
			margin: 33rpx 0;
			margin-bottom: 23rpx;
			margin-left: 40rpx;

			.left {
				border-radius: 50%;
				background-color: #E94A44;
				width: 12rpx;
				height: 12rpx;
				margin-right: 10rpx;
			}

			.right {
				text {
					@include fontStyle(32rpx, 700, #2E2727, 45rpx);
				}
			}
		}

		.select-area {
			background-color: #ffffff;

			.event-area {
				@include flexX;
				flex-wrap: wrap;
				box-sizing: border-box;
				padding-left: 40rpx;
				margin-top: 20rpx;

				.one {
					box-sizing: border-box;
					margin-right: 20rpx;
					margin-top: 20rpx;

					text {
						@include fontStyle(28rpx, 400, #B5B5B5, 40rpx);
						background: #F8F8F8;
						border-radius: 30rpx;
						padding: 5rpx 20rpx;
						box-sizing: border-box;
					}

					&.active {
						text {
							color: #ffffff;
							background: #E94A44;
						}
					}
				}
			}
		}

		.btn {
			width: 100%;
			background-color: transparent;
			// background-color: red;
			position: fixed;
			bottom: 0;
			height: 100rpx;
			@include flexY;
			justify-content: center;
			align-items: center;

			text {
				@include fontStyle(36rpx, 500, #ffffff, 50rpx);
				letter-spacing: 2px;
			}

			&.active {
				background-color: #E94A44;
			}
		}
	}
</style>