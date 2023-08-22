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
		<cover-view class="dingwei">
			<cover-image class="box" src="@/static/dingwei.png">
			</cover-image>
		</cover-view>
		<cover-view class="windows">
			<cover-view class="a">
				<cover-image class="box" src="@/static/location.png">
				</cover-image>
				<cover-view class="location">
					浙江宁波市鄞州区恒业大厦

				</cover-view>
			</cover-view>
			<cover-view class="distance">
				20km以内
			</cover-view>
			<cover-view class="__slider">
				<slider value="50" min="0" max="99"></slider>
			</cover-view>
		</cover-view>
		<cover-view class="map-area">
			<map style="width: 100%; height: 100%;" :latitude="latitude" :longitude="longitude" :markers="covers"
				:circles="circles">
			</map>
		</cover-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				id: 0, // 使用 marker点击事件 需要填写id
				title: 'map',
				latitude: 29.869082497353087,
				longitude: 121.54516635002204, // 宁波
				covers: [{
					latitude: 29.869082497353087,
					longitude: 121.54516635002204,
					iconPath: '/static/location.png',
					width: 64,
					height: 64
				}],
				circles: [{
					latitude: 29.869082497353087,
					longitude: 121.54516635002204,
					color: '#FFBDBB',
					// 填充颜色
					fillColor: '#FFBDBB40',
					// 圆半径
					radius: 500,
					// 边
					strokeWidth:0
				}],
				value: 20
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

		.map-area {
			height: 100%;
			width: 100%;
			z-index: 1;
		}

		.dingwei {
			position: fixed;
			right: 30rpx;
			bottom: 377rpx;

			.box {
				width: 84rpx;
				height: 84rpx;
			}
		}

		.windows {
			position: fixed;
			right: 30rpx;
			bottom: 77rpx;
			width: 690rpx;
			height: 300rpx;
			background: #FFFFFF;
			border-radius: 10rpx;

			.a {
				@include flexX;
				align-items: center;
				// position: absolute;
				margin-left: 10rpx;
				margin-top: 10rpx;

				.box {
					width: 64rpx;
					height: 64rpx;
					margin-right: 20rpx;
				}

				.location {
					@include fontStyle(32rpx, 700, #2E2727, 45rpx);

					letter-spacing: 1px;
					position: relative;
				}
			}

			.distance {
				@include fontStyle(28rpx, 400, #E94A44, 40rpx);
				letter-spacing: 1px;
				margin-left: 94rpx;
			}

			.__slider {
				position: absolute;
				bottom: 47rpx;
				margin: 0 60rpx;
				background: red;
			}
		}
	}
</style>