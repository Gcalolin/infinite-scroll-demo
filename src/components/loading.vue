<template>
	<div class="loading" v-show="loading">
		<span></span>
		<span></span>
		<span></span>
		<span></span>
		<span></span>
	</div>
</template>

<script>
	export default {
		props:{//父组件传过来的属性
			loading:{
				type:Boolean
			}
		}
	}
</script>

<style scoped>
	.loading{
		text-align:center;
		height: 40px;
		height: 40px;
		position: relative;
		
	}
	/*这里的dispaly:inline-block非常重要,span是行内元素，没有高度，必须设置成块级元素*/
	.loading span{
		width: 1px;
		height: 10px;
		background: #f60;
		display: inline-block; 
		animation: loading 1.4s ease-out infinite;
	}
	.loading span:nth-child(2){
		animation-delay:-1.2s;			
	}
	.loading span:nth-child(3){
		animation-delay:-1.0s;			
	}
	.loading span:nth-child(4){
		animation-delay:-0.8s;			
	}
	.loading span:nth-child(5){
		animation-delay:-0.6s;			
	}
	@keyframes loading{
		 0% {
            transform: scale(0.4);
        }
        25% {
            transform: scale(1);
        }
        50% {
            transform: scale(1.6);
        }
        75% {
            transform: scale(1);
        }
        100% {
            transform: scale(0.4);
        }
	}
</style>
