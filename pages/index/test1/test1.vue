<template>
	<view>
		<h2>x{{x}}</h2>
		<h2>y{{y}}</h2>
		<h2>z{{z}}</h2>
		<button type="primary" @click="button1">监听陀螺仪数据变化事件</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				x,
				y,
				z,
			}
		},
		methods: {
			button1()
			{
				uni.onGyroscopeChange((res)=>
				{
					console.log(x,y,z);
					this.x=x;
					this.y=y;
					this.z=z;
				})
			}
		}
	}
</script>

<style>

</style>
