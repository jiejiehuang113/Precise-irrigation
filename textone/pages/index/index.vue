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
		
	<view class="content" v-bind:class="className" v-on:click="open">
		<!--
		{{}}表示变量，{{title}}用于数据绑定title
		
		-->
		
		{{title}}
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
				title:"我的",
				className:'active'
			}
		},
		onLoad() {
			//做动态刷新
			setTimeout(()=>{
				this.title='hello 黄英杰'
			},3000)//延时3秒

		},
		//自定义方法，自定义事件
		methods: {
			open(){
				console.log('点击了');
				this.title='点击了'
			}

		}
	}
</script>

<style>

</style>
