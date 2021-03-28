<template>
	<!-- 第一个color是样式的属性名，第二个color是传入的属性名 -->
	<view class="btn-box" :style="{color:color }" @click="onClick">
		点击
	</view>
</template>

<script>
	export default {
		//接收属性
		props:{
			color:{
				type:String,
				default:'#000'
			}
			
		},
		data() {
			return {
				
			};
		},
		methods:{
			onClick(){
				console.log('我被点击了');
				//自定义事件   (change  -->  index.vue中的@change)
				this.$emit('change',this.color)
			}
		}
	}
</script>

<style>
	.btn-box{
		width: 200px;
		height: 100px;
		text-align: center;
		line-height: 100px;
		border: 1rpx red solid;
	}
</style>
