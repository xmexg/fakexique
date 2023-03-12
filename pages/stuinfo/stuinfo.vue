<template>
	<view class="page">
		<view><text class="v">{{info[ide].type}}</text></view>
		<view><text class="n">学号：</text><text class="v">{{info[ide].id}}</text></view>
		<view><text class="n">姓名：</text><text class="v">{{info[ide].name}}</text></view>
		<view><text class="n">性别：</text><text class="v">{{info[ide].sex}}</text></view>
		<view><text class="n">身份证号：</text><text class="v">{{info[ide].card}}</text></view>
		<view><text class="n">考生号：</text><text class="v">{{info[ide].exam}}</text></view>
		<view><text class="n">学制：</text><text class="v">{{info[ide].len}}</text></view>
		<view><text class="n">学院：</text><text class="v">{{info[ide].yard}}</text></view>
		<view><text class="n">入学年级：</text><text class="v">{{info[ide].in}}</text></view>
		<view><text class="n">专业：</text><text class="v">{{info[ide].sub}}</text></view>
		<view><text class="n">班级：</text><text class="v">{{info[ide].class}}</text></view>
		<view><text class="n">政治面貌：</text><text class="v">{{info[ide].face}}</text></view>
		<view><text class="n">民族：</text><text class="v">{{info[ide].nat}}</text></view>
		<view><text class="n">入学后照片：</text><text class="v phot">查看</text></view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				ide: 0,
				info: [
					{"type": "身份类型", "id": "学号", "name": "姓名", "sex": "性别", "card": "身份证号", "exam": "考生号", "len": "学制", "yard": "学院", "in": "入学年级", "sub": "专业", "class": "班级", "face": "政治面貌", "nat":"民族"}
				]
			}
		},
		methods: {
		},
		onLoad(){
			let that = this
			uni.getStorage({
				key: "stujson",
				success: function(res) {
					// 将获取到的数据转换成对象
					let data = JSON.parse(res.data)
					// 使用Object.assign()方法替换data中的info属性
					// that.$set(that, 'info', Object.assign({}, that.info, data))//无效
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
			// this.info = storstujson
		}
	}
</script>

<style>
	
	.page{
		width: 100vw;
		height: 100vh;
		background: #f2f2f2;
		display: flex;
		flex-direction: column;
	}
	
	.page > view{
		display: flex;
		flex-direction: row;
		align-items: center;
		padding: 5rpx 0;
		width: 100vw;
		height: 2em;
		padding: 5rpx 0;
		border: #f0f0f0 solid 1px;
		background: #FFFFFF;
	}
	
	.n{
		display: inline-block;
		color: #787878;
		min-width: 30%;
		position: relative;
		left: 2%;
		text-align: justify;
		text-align-last: justify;
	}
	
	.v{
		display: block;
		position: relative;
		left: 5%;
		
	}
	
	.phot{
		color: #005bf7;
	}
	
</style>
