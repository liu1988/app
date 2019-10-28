<template>
	<view>
		<uni-list>
		    <uni-list-item class="icon-img" title="标题文字" :show-arrow="false" note="描述信息" thumb="../../static/index/fate/1.jpg"></uni-list-item>
		    <uni-list-item title="标题文字" :show-arrow="false" note="描述信息" thumb="../../static/index/fate/2.jpg"></uni-list-item>
		    <uni-list-item title="标题文字" :show-arrow="false" :show-badge="true"  note="描述信息" thumb="../../static/index/fate/3.jpg"></uni-list-item>
		    <uni-list-item title="禁用状态" :show-arrow="false" :disabled="false" :show-badge="true"  note="描述信息" thumb="../../static/index/fate/4.jpg"></uni-list-item>
			<uni-list-item title="禁用状态" :show-arrow="false" :disabled="false" :show-badge="true"  note="描述信息" thumb="../../static/index/fate/5.jpg"></uni-list-item>
		</uni-list>
	</view>
</template>

<script>
	
	import uniList from "@dcloudio/uni-ui/lib/uni-list/uni-list.vue"
	import uniListItem from "@dcloudio/uni-ui/lib/uni-list-item/uni-list-item.vue"
	export default {
	    components: {uniList,uniListItem},
		
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
/* .icon-img{
	    height: 40px;
	    width: 40px;
} */
</style>
