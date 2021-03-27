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
		<!-- v-for  循环指令  -->
		<!-- item  : 被迭代的数组元素的别名 -->
		<!-- index : 下标别名 -->
		<view v-for="item in arr">
			{{item}}
		</view>
		<view v-for="(item,index) in arr">
			{{(index+1) +' '+ item}}
		</view>
		
		<view v-for="(item,value) in arr1">
			{{value +' : '+ item}}
		</view>
		<view v-for="(item,index) in data" :key="index">
			{{data}}
		</view>
		
	</view>
	
</template>

<script>
	export default {
		// 初始化数据方法
		
		//该方法不建议？ 保留上次的变量值，不会被初始化
		//data:{},
		
		//变量值会刷新
		
		data() {
			return {
				arr:['one','two','three'],
				
				arr1:{
					name:'xiaoming',
					age:18,
					type:'eat'
				},
				
				data:['第一个','第二个','第三个'],
			}
		},
		onLoad() {

		},
		//自定义方法，自定义事件
		methods: {

		}
	}
</script>

<style>

</style>
