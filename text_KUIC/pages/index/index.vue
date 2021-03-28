<template>
	<!--
		 1.模板语法
		 2.数据绑定
		 3.条件判断
		 4.列表渲染  通过数组来渲染我们的列表 
		 5.基础组件的使用
		 6.自定义组件的使用（简单的使用）
		 7.基础api的用法
		 8.条件编译
		 9.页面布局
		-->
		<!--
		:  v-bind: 的简写
		@  v-on:  的简写
		-->
		
	<view>
		<btn color="red" @change="change">
			点击
		</btn>
	</view>
	
</template>

<script>
	import btn from '@/components/btn/btn.vue'
	export default {
		//  注册新方法,自定义组件
		components:{
			btn
		},
		// 初始化数据方法
		
		//该方法不建议？ 保留上次的变量值，不会被初始化
		//data:{},
		
		//变量值会刷新
		
		data() {
			return {
			}
		},
		onLoad() {
			
		},
		//自定义方法，自定义事件
		methods: {
			change(e){
				console.log('我是页面的事件，我返回了：'+ e);
			}
		}
	}
</script>

<style>

</style>
