<template>
	<view>
		<!-- #ifdef MP-WEIXIN -->
		weixin
		<!-- #endif -->
		
		<!-- #ifdef H5 -->
		h5
		<!-- #endif -->	
		
	</view>
</template> 

<script>
	export default {
		data() {
			return {
				msg:null
			}
		},
		methods: {
			
		},
		onLoad(){
			uni.$on("change",(data)=>{
				this.msg = data  
			})
			// #ifdef MP-WEIXIN
			console.log("weixin")
			// #endif	
			// #ifdef H5
			console.log("h5")
			// #endif	
		},
		onShareAppMessage(res) {
			if (res.from === 'button') {// 来自页面内分享按钮
			  console.log(res.target)
			}
			return {
			  title: '自定义分享标题',
			  path: '/pages/test/test?id=123'
			}
		 }
	}
</script>

<style>

</style>
