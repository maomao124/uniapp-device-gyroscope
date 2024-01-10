<template>
	<view>
		<h2>x{{x}}</h2>
		<h2>y{{y}}</h2>
		<h2>z{{z}}</h2>
		<button type="primary" @click="button1">监听陀螺仪数据变化事件</button>
		<button type="primary" @click="button2">开始监听陀螺仪数据</button>
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
			},
			button2()
			{
				uni.startGyroscope({
					success: () => {
						uni.showToast({
							title:'成功'
						})
					},
					fail: () => {
						uni.showToast({
							icon:'fail',
							title:'失败'
						})
					}
				})
			}
		}
	}
</script>

<style>

</style>
