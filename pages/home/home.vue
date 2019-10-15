<template>
	<view>
		<!-- 顶部搜索栏 -->
		<div class="top-search">
		  <!--点击跳转至搜索页-->
		  <div class="flex-row center" routerLink="../../pages/search">
		    <span style="margin-left: .5em;">搜索</span>
		  </div>
		</div>
		<!-- 轮播图 -->
		<view class="uni-margin-wrap">
			<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
				<swiper-item v-for="item in banners" :key="item">
					<view class="swiper-item uni-bg-red">
						<image :src="item" mode=""></image>
					</view>
				</swiper-item>
			</swiper>
		</view>
		<!-- 标签列表 -->
		<div class="tags-list">
			<div class="tags-item" v-for="item in tagsList" :key="item">
				<navigator url="../shelf/shelf" class="tag">
					{{item}}
				</navigator>
			</div>
		</div>
		<!-- 主题列表 -->
		<div class="themes-list">
			<div class="themes-item" v-for="item in themesList" :key="item">
				<div class="theme">{{item}}</div>
			</div>
		</div>
		<!-- 推荐列表 -->
		<div class="recommon-list">
			<div class="recommon-title">
				<span>推荐商品</span>
				<span>=</span>
			</div>
			<div class="recommon-item" v-for="item in recommendList" :key="item">
				<div class="recommon">
					{{item}}
				</div>
			</div>
		</div>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				background: ['color1', 'color2', 'color3'],
				// 轮播参数
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				// banner图
				banners: [
					"../../static/images/banner/banner1.png",
					"../../static/images/banner/banner2.png",
					"../../static/images/banner/banner3.png",
					"../../static/images/banner/banner4.png"
				],
				// 标签列表
				tagsList: [
					"醉","里","悲","歌","惊","深","梦","+"
				],
				themesList: [
					"女鞋","男装","女包"
				],
				recommendList: [
					0,1,2,3,4,5,6,7,8,9
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.top-search{
	  background-color: white;
	  padding: .5em 1em;
	}
	.top-search>div{
		background-color: #F0F0F0;
		padding: .3em 1em;
		border-radius: 20px;
	}
	.swiper{
		height: 200px;
	}
	.swiper image{
		width: 100%;
	}
	/* 标签列表 */
	.tags-list, .themes-list, .recommon-list{
		width: 100%;
		display: flex;
		flex-wrap: wrap;
		border-bottom: .5rem solid #F0F0F0;
	}
	.tags-item{
		width: 25%;
		padding: .5rem;
		text-align: center;
		box-sizing: border-box;
	}
	.tags-item .tag{
		width: 50px;
		height: 50px;
		line-height: 50px;
		display: inline-block;
		border-radius: 50%;
		background-color: #F0AD4E;
	}
	/* 主题列表 */
	.themes-item{
		width: 50%;
		padding: .5rem;
		box-sizing: border-box;
	}
	.theme{
		min-height: 100px;
		box-shadow: 0 2px 3px 3px rgba(25,25,25,.1);
	}
	/* 推荐列表 */
	.recommon-title{
		width: 100%;
		padding: 0 1rem;
		display: flex;
		justify-content: space-between;
	}
	.recommon-item{
		width: 50%;
		padding: .5rem;
		box-sizing: border-box;
	}
	.recommon{
		height: 200px;
		box-shadow: 0 2px 3px 4px rgba(25,25,25,.1);
	}
</style>
