<template>
	<view class='content1'>
		<button @click="nihao">按钮</button>
		<child/>
	</view>
</template>

<script>
import child from '../../components/child.vue'
export default {
	data() {
		return {
		}
	},
	onLoad() {

	},
	onPullDownRefresh() {
		console.log('refresh');
		setTimeout(function () {
			uni.stopPullDownRefresh();
		}, 1000);
	},
	methods: {	
		nihao(){
			uni.$emit("change",{id:3})
		}
	},
	components:{
		child
	}
}

</script>

<style>
</style>
