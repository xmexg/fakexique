<template>
	<view class="page">
		<view class="topbar">
			<text class="title">提醒消息</text>
		</view>
		<view class="imgtext">
			<image src="/static/xiqueres/meim.jpg" mode="aspectFit"></image>
			<text>暂时没有数据</text>
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

<style>
	.page{
		display: flex;
		flex-direction: column;
		align-items: center;
		flex-wrap: wrap;
		width: 100%;
		height: 100vh;
	}
	
	.topbar{
		display: flex;
		position: absolute;
		top: 0px;
		width: 100%;
		background: #f0f0f0;
	}
	
	.title{
		color: #005bf7;
		position: relative;
		left: 5%;
		padding: 20rpx 0;
		border-bottom: #005bf7 solid 3px;
	}
	
	.imgtext{
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		width: 50%;
		height: 100%;
	}
	
	.imgtext image{
		width: 100%;
	}

</style>
