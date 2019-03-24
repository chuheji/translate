<template>
	<div id="translated">
		<p>{{translatedText}}</p>
		<van-loading type="spinner" color="white" />
		<van-loading color="white" />
	</div>
	
</template>
<script>
	export default{
		props: [
			'translatedText'
		],
		beforeUpdate() {
			
		}
	}
</script>
<style scoped>
	h2{
		color: #7777;
	}
	#translated{
		background-color: #eee;
		margin-top: 20px;
		padding: 20px 20px;
		height: 20px;
		font-size: 20px;
	}
</style>