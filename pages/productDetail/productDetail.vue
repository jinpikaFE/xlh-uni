<template>
	<view class="container">
		<u-swiper height="600" class="swiper-content" :list="list" />
		<view class="card">
			<view class="title">商品标题 商品标题 商品商品标题 商品标题 商品商品标题 商品标题 商品</view>
			<view class="title desc">商品标题 商品标题 商品商品标题 商品标题 商品商品标题 商品标题 商品</view>
			<view class="price">2999元</view>
			<view class="tags">
				<view class="tag-item">
					<image class="tag-icon" src="/static/true.svg" mode="aspectFill" />
					<text class="tag-name">七天无理由退换货</text>
				</view>
				<view class="tag-item">
					<image class="tag-icon" src="/static/true.svg" mode="aspectFill" />
					<text class="tag-name">48小时内发货</text>
				</view>
				<view class="tag-item">
					<image class="tag-icon" src="/static/true.svg" mode="aspectFill" />
					<text class="tag-name">免运费</text>
				</view>
			</view>
		</view>
		<view class="card">
			<uni-list>
				<uni-list-item title="已选择" rightText="原木色，150*200cm，1件" :showArrow="true" />
				<uni-list-item title="发货" :showArrow="true">
					<template v-slot:footer>
						<view class="slot-footer">
							<text>张三</text>
							<text class="is-verify">未实名</text>
						</view>
					</template>
				</uni-list-item>
			</uni-list>
		</view>
		<uni-section title="商品详情" type="line" padding><image class="detail-img" src="/static/true.svg" mode="aspectFill" /></uni-section>
		<u-back-top :scroll-top="scrollTop" icon="arrow-up-fill" icon-style="color: #f5574e"></u-back-top>
	</view>
</template>

<script lang="ts">
export default {
	data() {
		return {
			list: [
				{
					image: 'https://cdn.uviewui.com/uview/swiper/1.jpg',
					title: '昨夜星辰昨夜风，画楼西畔桂堂东'
				},
				{
					image: 'https://cdn.uviewui.com/uview/swiper/2.jpg',
					title: '身无彩凤双飞翼，心有灵犀一点通'
				},
				{
					image: 'https://cdn.uviewui.com/uview/swiper/3.jpg',
					title: '谁念西风独自凉，萧萧黄叶闭疏窗，沉思往事立残阳'
				}
			],
			scrollTop: 0
		};
	},
	onPageScroll(e) {
		this.scrollTop = e.scrollTop;
	}
};
</script>

<style lang="scss">
@mixin ellipsis-line {
	overflow: hidden;
	text-overflow: ellipsis;
	white-space: nowrap;
}

.container {
	min-height: 100vh;
	background-color: #f5f5f5;

	.card {
		padding: 0 15px;
		background-color: #fff;
		margin-bottom: 23px;
	}

	.title {
		@include ellipsis-line;
		width: 100%;
		color: rgba(0, 0, 0, 1);
		font-size: 16px;
		font-weight: bolder;
		padding-top: 20px;

		&.desc {
			color: rgba(166, 166, 166, 1);
			font-size: 14px;
			font-weight: unset;
			padding-top: 5px;
		}
	}

	.price {
		margin-top: 21px;
		color: #d43030;
		font-size: 18px;
		font-weight: bold;
	}

	.tags {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		margin-top: 13px;
		padding-bottom: 18px;

		.tag-item {
			display: flex;
			flex-direction: row;
			margin-right: 11px;
			margin-bottom: 5px;

			.tag-icon {
				width: 16px;
				height: 16px;
				margin-right: 5px;
			}

			.tag-name {
				color: #ff533c;
				font-size: 12px;
			}
		}
	}

	.detail-img {
		width: 100%;
	}

	.u-back-top {
		background-color: rgba(225, 225, 225, 0.8);
	}

	::v-deep .uni-list--border-top {
		display: none;
	}

	::v-deep .uni-list--border-bottom {
		display: none;
	}

	::v-deep .uni-section .uni-section-header__decoration {
		background-color: #ff533c;
	}
}
</style>
