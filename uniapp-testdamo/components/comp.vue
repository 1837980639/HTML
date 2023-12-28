<template>
	<view class="content">
		<button type="primary" @click="sendMsg">发送消息</button>
	</view>
</template>

<script>
	export default {
		name:"comp",
		props:{
			name:String
		},
		data() {
			return {
				
			};
		},
		methods:{
			sendMsg(){
				//子传父
				this.$emit('getMsg',"我是子"+this.name);
			}
				
		}
	}
</script>

<style>

</style>