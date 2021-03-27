<template>
	<!--
		 1.模板语法
		 2.数据绑定
		 3.条件判断
		 4.列表渲染
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
		<view>一直显示标题</view>
		<!-- v-if 如果表达式返回true，则正常渲染内容，反之则无 -->
		<view v-if="showif">动态显示标题</view>
		
		<view>{{showif?'这是真值':'这是假值'}}</view><!-- ?'{真值时反应}':'假值时反应'  ? 为判断 -->
		<button type="default" @click="open">请点击</button>
		
		<view>
			<!--
			if(){}else{}
			if(){}else if(){}else{}
			-->
			<view v-if="show2if">view_one</view>
			<view v-else>view_two</view><!-- 同一个判断，else反应 -->
		</view>
		<button type="default" @click="open2">第二点击事件</button>
		
		<view>
			<!--
			if(){}else if(){}else{}
			-->
			<view v-if="show3if === 'one'">view_one</view>
			<view v-else-if="show3if === 'two'">view_two</view>
			<view v-else>view_three</view>
		</view>
		<button type="default" @click="open3">第三点击事件</button>
		
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
				showif:true,
				show2if:true,
				show3if:'one'
			}
		},
		onLoad() {

		},
		//自定义方法，自定义事件
		methods: {
			open(){
				console.log(this.showif)//获取showif的值
				this.showif = !this.showif
			},
			
			open2(){
				console.log(this.show2if)
				this.show2if = !this.show2if
			},
			
			open3(){
				console.log(this.show3if)
				this.show3if = 'two'
			}
		}
	}
</script>

<style>

</style>
