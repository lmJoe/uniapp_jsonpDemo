# uniapp_jsonpDemo
使用vue-jsonp对jsonp接口做数据请求，经测试不适用于小程序
<template>
	<view>
		
	</view>
</template>

<script>
	import {jsonp} from 'vue-jsonp'
	export default {
		data() {
			return {
				
			}
		},
		mounted() {
			this.getList();
		},
		methods: {
			getList(index) {
				const url = '';
				const UnixTime = (new Date()).valueOf();
				const paramsData = {
					dataType:'h5_sensorindex',
					pageSize:16,
					pageIndex:1,
					channelId:100,
					distinctid:'',
					jsoncallback:'jsoncallback'+UnixTime,
					output: 'jsonp',
					callbackQuery: "callbackParam",//最重要的
				    callbackName: 'jsoncallback'+UnixTime,//最重要的
				}
				jsonp(url,paramsData,30000)
					.then((response)=>{ 
						// 移除监听事件
						console.log("response",response)
					}).catch(err => { 
						console.log(err) 
					}) 
			},
		}
	}
</script>

<style>

</style>
