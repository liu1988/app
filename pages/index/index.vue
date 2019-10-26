<template>
	<view>

		<view>
			<view>
				<!-- scroll-left="120"；右边的元素上来的距离 -->
				<scroll-view class="scroll-view_H" scroll-x="true" show-scrollbar="false" scroll-with-animation="true">
					<view class="scroll-view-item_H" v-for="(huadong,index) in huadongs" :key="index">
						<view>
							<image :src="huadong.img" mode="scaleToFill"></image>
						</view>
						<view class="scroll-text-info">
							<view>
								<text class="btn_text_name">{{huadong.name}}</text>
								<text class="btn_texts">在线</text>
							</view>

							<view>{{huadong.age}}岁|{{huadong.height}}|{{huadong.edu}}|{{huadong.salary}}元</view>
						</view>
					</view>
				</scroll-view>
			</view>
		</view>

	</view>
</template>
<script>
	import uniTag from '@dcloudio/uni-ui/lib/uni-tag/uni-tag.vue'
	export default {
		components: {
			uniTag
		},
		data() {
			return {
				huadongs: [{
						img: '../../static/index/fate/1.jpg',
						name: '杨幂',
						age: '20',
						height: '160cm',
						edu: '本科',
						salary: '5000~8000'
					},
					{
						img: '../../static/index/fate/2.jpg',
						name: '舟舟',
						age: '20',
						height: '160cm',
						edu: '本科',
						salary: '5000~8000'
					},
					{
						img: '../../static/index/fate/3.jpg',
						name: '舟舟',
						age: '20',
						height: '160cm',
						edu: '本科',
						salary: '5000~8000'
					},
					{
						img: '../../static/index/fate/4.jpg',
						name: '舟舟',
						age: '20',
						height: '160cm',
						edu: '本科',
						salary: '5000~8000'
					},
					{
						img: '../../static/index/fate/5.jpg',
						name: '舟舟',
						age: '20',
						height: '160cm',
						edu: '本科',
						salary: '5000~8000'
					}
				]
			}
		},
		methods: {

		}
	}
</script>

<style>
	.scroll-view_H {
		/* 文本不会换行，文本会在在同一行上继续，直到遇到 <br> 标签为止。 */
		white-space: nowrap;
		width: 100%;
		height: 100%;
	}

	.scroll-view-item_H {
		display: inline-block;
		width: 100%;
		height: 100%;
		margin: 15% 2% 2% 2%;
	}

	.scroll-view-item_H view {
		box-sizing: border-box;
	}

	.scroll-view-item_H view:nth-child(1) {
		width: 800upx;
		height: 900upx;
	}

	.scroll-view-item_H view:nth-child(1) image {
		width: 90%;
		height: 100%;
		border-radius: 10rpx;
	}

	.scroll-text-info {
		width: 100px;
		margin-top: 20upx;
	}

	.scroll-text-info view:nth-child(1) {
		font-size: 36upx;
		width: 100%;
		height: 30upx;
		margin-left: 20rpx;
		font-weight: 600;
		letter-spacing: 2rpx;
		line-height: 40rpx;
	}

	.scroll-text-info view:nth-child(2) {
		font-size: 26upx;
		width: 100%;
		height: 30upx;
		margin-top: 20upx;
		margin-left: 20rpx;
		letter-spacing: 2rpx;
		line-height: 40rpx;
	}

	.btn_text_name {
		display: inline-block;
		vertical-align:middle
	}

	.btn_texts {
		width: 50rpx;
		height: 40rpx;
		background: #007AFF;
		text-align: center;
		display: inline-block;
		border-radius: 8rpx;
		font-size: 12px;
		color: #F8F8F8 ;
		vertical-align:middle;
		margin-left:10rpx
	}
</style>
