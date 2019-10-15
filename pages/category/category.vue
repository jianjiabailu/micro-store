<template>
	<view class="page-category">
		<!-- 一级分类 -->
		<div class="classify-list">
			<div class="classify-item" v-for="(item,index) in classifyList" :key="item.id">
				<div class="classify" @click="currentClassify=index">
					{{item.name}}
				</div>
			</div>
		</div>
		<!-- 二级分类 -->
		<div class="level-list">
			<div class="level-item" v-for="(item,index) in classifyList[currentClassify].level" :key="item.id">
				<div class="level">
					{{item.name}}
				</div>
			</div>
		</div>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				currentClassify: 0,
				classifyList: [
					{
						id: '01',
						name: "女装",
						level: [
							{
								id: "0101",
								name: "女装1",
							},{
								id: "0102",
								name: "女装2",
							},
						]
					},
					{
						id: '02',
						name: "男装",
						level: [
							{
								id: "0201",
								name: "男装1",
							},{
								id: "0202",
								name: "男装2",
							},{
								id: "0203",
								name: "男装3",
							},{
								id: "0204",
								name: "男装3",
							},{
								id: "0205",
								name: "男装2",
							},{
								id: "0206",
								name: "男装2",
							},{
								id: "0207",
								name: "男装2",
							},{
								id: "0208",
								name: "男装2",
							}
						]
					}
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.page-category{
		display: flex;
		flex-direction: row;
		align-items: stretch;
	}
	.classify-list{
		width: 80px; height: 100%;
		overflow-y: auto;
		border-right: .5rem solid #F0F0F0;
	}
	.classify-item{
		padding: .3rem .5rem;
		border-bottom: 1px solid #F0F0F0;
	}
	.level-list{
		flex: 1;
		display: flex;
		flex-wrap: wrap;
	}
	.level-item{
		width: 33.333%;
		text-align: center;
		box-sizing: border-box;
	}
	.level{
		height: 50px;
	}
</style>
