<template>
	<!--
		 1.模板语法
		 2.数据绑定
		 3.条件判断
		 4.列表渲染  通过数组来渲染我们的列表 Y
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
		<button type="default" @click="input">点击</button>
		<input type="text" :value="value1" />
		<input type="text" v-model="value2" /><!-- 双向绑定 -->
		<view>
			当前的值是：{{value1}}
		</view>
		<view>
			当前的值是：{{value2}}
		</view>
		
		<scroll-view class="height" scroll-y="true" >
			<view>
				<view class="uni-form-item uni-column">
					<view class="title">
						可自动聚焦的input
					</view>
					<input type="uni-input" focus placeholder="自动获得焦点" />
				</view>
				<view class="uni-form-item uni-column">
				                <view class="title">键盘右下角按钮显示为搜索</view>
				                <input class="uni-input" confirm-type="search" placeholder="键盘右下角按钮显示为搜索" />
				            </view>
				 <view class="uni-form-item uni-column">
				                <view class="title">控制最大输入长度的input</view>
				                <input class="uni-input" maxlength="10" placeholder="最大输入长度为10" />
				            </view>
				            <view class="uni-form-item uni-column">
				                <view class="title">实时获取输入值：{{inputValue}}</view>
				                <input class="uni-input" @input="onKeyInput" placeholder="输入同步到view中" />
				            </view>
				            <view class="uni-form-item uni-column">
				                <view class="title">控制输入的input</view>
				                <input class="uni-input" @input="replaceInput" v-model="changeValue" placeholder="连续的两个1会变成2" />
				            </view>
				            <!-- #ifndef MP-BAIDU -->
				            <view class="uni-form-item uni-column">
				                <view class="title">控制键盘的input</view>
				                <input class="uni-input" ref="input1" @input="hideKeyboard" placeholder="输入123自动收起键盘" />
				            </view>
				            <!-- #endif -->
				            <view class="uni-form-item uni-column">
				                <view class="title">数字输入的input</view>
				                <input class="uni-input" type="number" placeholder="这是一个数字输入框" />
				            </view>
				            <view class="uni-form-item uni-column">
				                <view class="title">密码输入的input</view>
				                <input class="uni-input" password type="text" placeholder="这是一个密码输入框" />
				            </view>
				            <view class="uni-form-item uni-column">
				                <view class="title">带小数点的input</view>
				                <input class="uni-input" type="digit" placeholder="带小数点的数字键盘" />
				            </view>
				            <view class="uni-form-item uni-column">
				                <view class="title">身份证输入的input</view>
				                <input class="uni-input" type="idcard" placeholder="身份证输入键盘" />
				            </view>
				            <view class="uni-form-item uni-column">
				                <view class="title">控制占位符颜色的input</view>
				                <input class="uni-input" placeholder-style="color:#F76260" placeholder="占位符字体是红色的" />
				            </view>
			</view>
		</scroll-view>
		
		<scroll-view class="height" scroll-y="true" @scroll="scroll">
			<view v-for="item in 100">{{item}}</view>
		</scroll-view>
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
				value1:'adsfg',
				value2:'hello uni-app',
				title: 'input',
				focus: false,
				inputValue: '',
				changeValue: ''
			}
		},
		onLoad() {
			
		},
		//自定义方法，自定义事件
		methods: {
			scroll(e){
				console.log(e)
			},
			
			input(){
				this.value2 = 'hello two'
			},
			onKeyInput: function(event) {
			            this.inputValue = event.target.value
			        },
			replaceInput: function(event) {
				var value = event.target.value;
				if (value === '11') {
					this.changeValue = '2';
					}
				},
			hideKeyboard: function(event) {
				if (event.target.value === '123') {
			        uni.hideKeyboard();
			        }
			    }
			
		}
	}
</script>

<style>
	.height{
		height: 500px;
		border: 1px red solid;
	}

</style>
