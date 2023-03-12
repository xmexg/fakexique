<template>
	<view class="page">
		<view class="top">
			<p class="yuan"></p>
			<view class="topimgview">
				<image src="/static/xiqueres/head.jpg" mode="aspectFill"></image>
			</view>
			<text>{{info[0].name}}</text>
		</view>
		<view class="part"></view>
		<view class="list">
			<view class="lsv" @tap="showstuinfo">
				<image class="li_div listimg" src="/static/xiqueres/dwJ.png" mode="aspectFit"></image>
				<text class="li_div listtl">个人信息</text>
				<text class="li_div listtr">></text>
			</view>
			<view class="lsv">
				<image class="li_div listimg" src="/static/xiqueres/OnF.png" mode="aspectFit"></image>
				<text class="li_div listtl">账号安全</text>
				<text class="li_div listtr">></text>
			</view>
			<view class="lsv">
				<image class="li_div listimg" src="/static/xiqueres/DHG.png" mode="aspectFit"></image>
				<text class="li_div listtl">设置</text>
				<text class="li_div listtr">></text>
			</view>
			<view class="lsv">
				<image class="li_div listimg" src="/static/xiqueres/J4f.png" mode="aspectFit"></image>
				<text class="li_div listtl">帮助与反馈</text>
				<text class="li_div listtr">></text>
			</view>
			<view class="lsv" @tap="about">
				<image class="li_div listimg" src="/static/xiqueres/m2v.png" mode="aspectFit"></image>
				<text class="li_div listtl">关于</text>
				<text class="li_div listtr">></text>
			</view>
			<view class="lsv" @tap="edit">
				<image class="li_div listimg" src="/static/xiqueres/36q.png" mode="aspectFit"></image>
				<text class="li_div listtl">退出登录</text>
				<text class="li_div listtr">></text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				name: "姓名",
				info: [
					{"type": "身份类型", "id": "学号", "name": "姓名", "sex": "性别", "card": "身份证号", "exam": "考生号", "len": "学制", "yard": "学院", "in": "入学年级", "sub": "专业", "class": "班级", "face": "政治面貌", "nat":"民族"}
				]
			}
		},
		onLoad() {
			let that = this
			uni.getStorage({
				key: "stujson",
				success: function(res) {
					// 将获取到的数据转换成对象
					let data = JSON.parse(res.data)
					that.name = data.name//部分设备不起作用
					// 更新data中的info属性
					that.info[0].type = data.type
					that.info[0].id = data.id
					that.info[0].name = data.name
					that.info[0].sex = data.sex
					that.info[0].card = data.card
					that.info[0].exam = data.exam
					that.info[0].len = data.len
					that.info[0].yard = data.yard
					that.info[0].in = data.in
					that.info[0].sub = data.sub
					that.info[0].class = data.class
					that.info[0].face = data.face
					that.info[0].nat = data.nat
				}
			})
		},
		methods: {
			showstuinfo(){
				uni.navigateTo({
					url: "/pages/stuinfo/stuinfo"
				})
			},
			about(){
				uni.navigateTo({
					url: "/pages/about/about"
				})
			},
			edit(){
				uni.navigateTo({
					url: "/pages/edit/edit"
				})
				
			}
		}
	}
</script>

<style>
	.page {
		display: flex;
		flex-direction: column;
		width: 100vw;
		height: 100vh;
	}

	.top {
		display: flex;
		position: relative;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		width: 100%;
		height: 20%;
		background: linear-gradient(180deg, #50c0f3, #130cb7);
		overflow: hidden;
	}

	.yuan {
		width: 150%;
		height: 100%;
		border-radius: 100%;
		background: #FFFFFF;
		position: absolute;
		bottom: -50%;
	}

	.topimgview {
		width: 20vw;
		height: calc(20vw);
		border-radius: 50%;
		border: #FFFFFF solid 2rpx;
		overflow: hidden;
		background: #52e5e7;
	}

	.topimgview image {
		width: 100%;
		height: 100%;
	}

	.top text {
		display: flex;
		position: absolute;
		bottom: 0;
	}

	.part {
		width: 100%;
		height: 20rpx;
		background: #f8f9fa;
	}

	.list {
		display: flex;
		flex-direction: column;
		flex-wrap: wrap;
		width: 100%;
	}

	.lsv{
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		align-items: center;
		width: 100%;
		height: 50rpx;
		border: #f0f0f0 solid 1px;
		padding: 10rpx 0;
		
	}
	
	.listimg{
		height: 50rpx;
		width: 15%;
	}
	
	.listtr{
		position: absolute;
		right: 5%;
		color: #868e96;
	}
	
	.li_div {
		display: flex;
	}
</style>
