<template>
	<view class="content">
		<image class="logo" src="/static/xiqueres/top.jpg" mode="aspectFit"></image>
		<view class="flview">
			<view class="fl" v-for="(item, index) in functionlist" :key="item.title">
				<view class="fl_block">
					<image class="fl_block_img" :src="item.icon" mode="aspectFit"></image>
					<text>{{item.name}}</text>
				</view>
			</view>
		</view>
		<view class="N">
			<image src="/static/xiqueres/N.jpg" mode="aspectFit" scoped></image>
			<text>暂无数据</text>
		</view>
		<view class="todaysd">
			<text class="todaysdti">今日课表</text>
			<view class="sche" id="sche" v-for="item in schedule">
				<view class="schename">{{item.name}}</view>
				<view class="scheloc">{{item.loc}}</view>
				<view class="scheilb schetime">{{item.time}}节</view>
				<view class="scheilb schestunum">{{item.stunum}}人</view>
				<view class="scheright">教学互动</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				functionlist: [
					{name: "蹭课",icon: "/static/xiqueres/ck_.jpg"},
					{name: "查看培训方案",icon: "/static/xiqueres/ckfa_.jpg"},
					{name: "考试安排",icon: "/static/xiqueres/ksap_.jpg"},
					{name: "空闲教室",icon: "/static/xiqueres/J3e.png"},
					{name: "学业成绩",icon: "/static/xiqueres/yp9.png"},
					{name: "全部服务",icon: "/static/xiqueres/JAz.png"},
					{name: "",icon: ""},
					{name: "",icon: ""}
				],
				schedule: [
					{name:"大学英语",loc:"@本校区E02-203教室",time:"1-2",stunum:"77"},
					{name:"形式与政策",loc:"@本校区E02-203教室",time:"3-4",stunum:"55"},
					{name:"程序设计基础",loc:"@本校区E02-203教室",time:"5-6",stunum:"102"},
					{name:"军事理论",loc:"@本校区E02-203教室",time:"7-8",stunum:"55"}
				]
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: flex-start;
		background: #f8f9fa;
		width: 100vw;
		height: 100vh;
		padding-bottom: var(–-window-bottom);
	}

	.logo {
		border-radius: 10px;
		min-width: 96vw;
		min-height: calc(96vw/103*42);
	}

	.flview {
		border-radius: 10rpx;
		margin: 10rpx 0;
		width: 96%;
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		background: #FFFFFF;
	}

	.fl {
		width: 25%;
		display: flex;
	}

	.fl_block {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		width: 100%;
		height: 170rpx;
		font-size: 25rpx;
		border: 1rpx solid #f8f9fa;
	}

	.fl_block_img {
		width: 70rpx;
		height: 100rpx;
	}

	.N{
		border-radius: 10rpx;
		margin: 10rpx 0;
		width: 96%;
		height: 50rpx;
		background: #FFFFFF;
		display: flex;
		flex-direction: row;
	}
	
	.N image{
		height: 90%;
		width: 10%;
		display: flex;
	}
	
	.N text{
		display: flex;
	}
	
	.todaysd{
		border-radius: 10rpx;
		margin: 10rpx 0;
		width: 96%;
		background: #FFFFFF;
	}
	
	.todaysdti{
		display: flex;
		position: relative;
		left: 3%;
		border-left: 10rpx solid #4263eb;
		margin: 20rpx 0;
	}
	
	.sche{
		position: relative;
		border-radius: 10rpx;
		margin: 10rpx 0;
		padding: 20rpx 0;
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		background: #FFFFFF;
		width: 100%;
	}
	
	#sche:nth-child(2){
		background: #cab2de;
	}
	
	#sche:nth-child(3){
		background: #f6c5cb;
	}
	
	#sche:nth-child(4){
		background: #c6d8f7;
	}
	
	#sche:nth-child(5){
		background: #ffeecc;
	}
	
	#sche:nth-child(2) .scheilb{
		color: #7a00de;
		border-color: #7a00de;
	}
	
	#sche:nth-child(3) .scheilb{
		color: #f61414;
		border-color: #f61414;
	}
	
	#sche:nth-child(4) .scheilb{
		color: #005bf7;
		border-color: #005bf7;
	}
	
	#sche:nth-child(5) .scheilb{
		color: #ffaa00;
		border-color: #ffaa00;
	}
	
	.schename{
		width: 96%;
		position: relative;
		left: 4%;
		padding: 5rpx 0 5rpx 0;
	}
	
	.scheloc{
		font-size: 0.7em;
		width: 96%;
		padding: 5rpx 0 5rpx 0;
		color: #4263eb;
		position: relative;
		left: 4%;
	}
	
	.scheilb{
		border-radius: 5px;
		border-width: 2rpx;
		border-style: solid;
		position: relative;
		left: 4%;
		margin: 0 3% 0 0;
		padding: 0 10rpx;
	}
	
	.scheright{
		background: #005bf7;
		color: #FFFFFF;
		position: absolute;
		right: 5%;
		padding: 10rpx;
		border-radius: 5px;
		top: 33%;
	}
	
</style>
