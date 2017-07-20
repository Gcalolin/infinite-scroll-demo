<template>
	<div>
		<ul v-infinite-scroll="loadMore"
		infinite-scroll-disabled="busy"
		infinite-scroll-distance="30"
		infinite-scroll-immediate-check="fasle">
			<li v-for="item in items">{{ item }}</li>
		</ul>
		<loading :loading="busy"></loading>
	</div>
</template>

<script>
import loading from '../components/loading.vue'

	export default {
		components:{
			loading
		},
		data(){
			return {
				items:[1,2,3],
				loading:true,
				busy:true
			}
		},
		mounted(){
			this.$nextTick(function(){
				console.log('mounted');
				this.loadMore();
			})
		},
		methods:{
			getRanArr(num=20){
				var arr=[]
				for (var i = num - 1; i >= 0; i--) {
					arr.push(Math.round(Math.random()*100))
				}
				return arr
			},
			loadMore(){
				console.log('loadMore...');
				this.busy = this.loading = true;
				let _this_ = this;
				setTimeout(function(){
					_this_.items = _this_.items.concat(_this_.getRanArr(20));
					_this_.loading = _this_.busy = false;
				},1000)
			}
		}
	}
</script>


<style scoped>
	ul{
		padding: 0;
		margin: 0;
	}
	ul li{
		height: 30px;
		text-align: center;
		line-height: 30px;
		list-style: none;
	}
	ul li:nth-child(odd){
		background-color: #eee;
	}
</style>