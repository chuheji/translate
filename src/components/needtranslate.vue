<template>
	<div id="needtranslate">
		<form @submit='translate'>
			<input class="input" type="text" v-model='needTranslateText' placeholder="请输入要翻译的内容">
			<span>翻译为</span>
			<select class="select" v-model='language'>
				<option value="en">英语</option>
				<option value="ko" selected="selected">韩语</option>
				<option value="ja">日语</option>
				<option value="fr">法语</option>
				<option value="ru">俄语</option>
				<option value="es">西班牙语</option>
			</select>
			<input type="submit" class="submit" value="翻译">
		</form>
	</div>
	
</template>
<script>
	export default{
		data(){
			return {
				needTranslateText: '',
				language: ''
			}
		},
		methods: {
			translate(e){
				// console.log(this.needTranslateText)
				e.preventDefault()
				this.$emit('submitform',this.needTranslateText,this.language)
			}
		}
	}
</script>
<style scoped>
	#needtranslate{
		background-color: #eee;
		padding: 40px 30px;
	}
	.input{
		padding-left: 5px;
		height: 35px;
		border-radius:5px;
		outline:none;
		border:1px solid #a1a1a1;
	}
	.select{
		padding-left: 5px;
		height: 35px;
		border-radius: 5px;
		outline:none;
		border:1px solid #a1a1a1;
	}
	.submit{
		padding: 0 15px;
		height: 35px;
		border-radius: 5px;
		outline:none;
		border:1px solid #a1a1a1;
		background-color: #fff;
		cursor: pointer;
		/* text-align: center; */

	}
</style>