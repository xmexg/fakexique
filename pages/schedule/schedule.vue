<template>
	<view>
		<view class="text-area">
			<text class="errortext">{{errortext}}</text>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				errortext: "访问学校课程表出错，请与学校管理员联系。"
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.errortext{
		display: flex;
		background: #f6bbbb;
		color: #f60000;
		width: 100%;
	}

</style>
