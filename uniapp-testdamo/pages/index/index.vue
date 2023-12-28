<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<comp :name="name" @getMsg="openMsg"></comp>
	</view>
</template>

<script>
	import comp from '../../components/comp.vue'
	export default {
		components:{
			comp
		},
		data() {
			return {
				title: 'Hello',
				name:"我是父"
			}
		},
		onLoad() {
			this.loadData()
		},
		methods: {
			loadData(){
				uni.request({
					url:'http://www.shoespaint.com/test.php',
					method:'POST',
					success:res=>{
						console.log(res)
					},
					fail:err=>{
						console.log(err)
					}
				})
			},
			// 接受子传过来的参数
			openMsg(msg){
				console.log(msg)
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
