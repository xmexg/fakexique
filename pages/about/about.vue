<template>
	<view class="page">
		<text>这是一个喜鹊儿仿制品</text>
		<text>他可以自定义你的信息以绕过迟到检查</text>
		<text>点击"退出登录"可以编辑信息</text>
		<text>项目地址：
			<text id="url">
				<a href="https://github.com/xmexg/fakexique">github (https://github.com/xmexg/fakexique)</a>
				<a href="https://gitee.com/vinamex/fakexique">gitee (https://gitee.com/vinamex/fakexique)</a>
			</text>
		</text>
		
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
		width: 100%;
	}
	
	.page > text{
		width: 100%;
		padding: 5rpx 0;
		margin: 5rpx 0;
		background: #f5fcff;
	}
	
	#url{
		display: flex;
		flex-direction: column;
		width: 100%;
		margin: 0 5rpx;
	}
	
	#url a{
		display: inline-block;
		width: 100%;
	}
</style>
