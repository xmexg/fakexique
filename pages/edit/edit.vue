<template>
	<view class="content">
		<form class="page" @submit="savedata">
			<view class="ls"><text class="n">用户类型：</text><input class="v" :placeholder="info[0].type" name="type"></input></view>
			<view class="ls"><text class="n">学号：</text><input class="v" :placeholder="info[ide].id" name="id"></input></view>
			<view class="ls"><text class="n">姓名：</text><input class="v" :placeholder="info[ide].name" name="name"></input></view>
			<view class="ls"><text class="n">性别：</text><input class="v" :placeholder="info[ide].sex" name="sex"></input></view>
			<view class="ls"><text class="n">身份证号：</text><input class="v" :placeholder="info[ide].card" name="card"></input></view>
			<view class="ls"><text class="n">考生号：</text><input class="v" :placeholder="info[ide].exam" name="exam"></input></view>
			<view class="ls"><text class="n">学制：</text><input class="v" :placeholder="info[ide].len" name="len"></input></view>
			<view class="ls"><text class="n">学院：</text><input class="v" :placeholder="info[ide].yard" name="yard"></input></view>
			<view class="ls"><text class="n">入学年级：</text><input class="v" :placeholder="info[ide].in" name="in"></input></view>
			<view class="ls"><text class="n">专业：</text><input class="v" :placeholder="info[ide].sub" name="sub"></input></view>
			<view class="ls"><text class="n">班级：</text><input class="v" :placeholder="info[ide].class" name="class"></input></view>
			<view class="ls"><text class="n">政治面貌：</text><input class="v" :placeholder="info[ide].face" name="face"></input></view>
			<view class="ls"><text class="n">民族：</text><input class="v" :placeholder="info[ide].nat" name="nat"></input></view>
			<view class="ls formbuview"><button form-type="submit" id="formbusb">保存</button><button form-type="reset">取消</button></view>
		</form>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				ide: 0,
				info: [
					{type: "身份类型", id: "学号", name: "姓名", sex: "性别", card: "身份证号", exam: "考生号", len: "学制", yard: "学院", in: "入学年级", sub: "专业", class: "班级", face: "政治面貌", nat:"民族"}
				]
			}
		},
		onLoad(){
			let that = this
			uni.getStorage({
				key: "stujson",
				success: function(res){
					// 将获取到的数据转换成对象
					let data = JSON.parse(res.data)
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
			savedata(e){
				let jsondata = JSON.stringify(e.detail.value)
				uni.setStorage({
					key: "stujson",
					data: jsondata,
					success: function(){
						console.log("保存成功")
					}
				})
			}
		}
	}
</script>

<style>
	.content{
		width: 100vw;
		height: 100vh;
		background: #f2f2f2;
		display: flex;
	}
	
	.page{
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;	
	}
	
	.ls{
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
		display: inline-block;
		position: relative;
		left: 5%;
		
	}
	
	.formbuview{
		height: auto;
	}
	
	#formbusb{
		width: 100%;
		height: 100%;
	}
	
</style>
