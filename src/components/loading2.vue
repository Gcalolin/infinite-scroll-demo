<template>
	<div class="loading" v-show='loading'>
		<span></span>
		<span></span>
		<span></span>
		<span></span>
		<span></span>
	</div>
</template>

<script>
	export default {
		props:{
			loading:{
				type:Boolean
			}
		}
	}
</script>

<style scoped>
	.loading{
		height: 12px;
		width: 100;
		text-align: center;
	}
	.loading span {
		width: 10px;
		height: 10px;
		background: #000;
		border-radius: 50%;
		display: inline-block;
	}
	.loading span:first-child{
		animation: loading-1 infinite 1.5s linear;
	}
	.loading span:last-child{
		/*animation: name duration timing-function delay iteration-count direction;*/
		animation: loading-2 infinite -0.75s 1.5s linear;
	}
	@keyframes loading-1 {
		0%{
			transform: translate(0px,0px);
		}
		25%{
			transform: translate(-30px,0px);
		}
		50%{
			transform: translate(0px,0px);
		}
		
		100%{
			transform: translate(0px,0px);
		}
	}
	@keyframes loading-2 {
		0%{
			transform: translate(0px,0px);
		}
		25%{
			transform: translate(30px,0px);
		}
		50%{
			transform: translate(0px,0px);
		}
		
		100%{
			transform: translate(0px,0px);
		}
	}
</style>