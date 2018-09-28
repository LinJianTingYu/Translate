<template>
  <div class="TranlateForm">
  	<form v-on:submit.prevent="responsetext">
  		<input type="text" v-model="textTranslate" placeholder="请输入文字" >
		<select v-model="language">
			<option value="en" checked>English</option>
			<option value="ru">Russian</option>
			<option value="ko">Korean</option>
			<option value="ja">Janpenese</option>
		</select>
  		<input type="submit">
  	</form>
  </div>
</template>

<script>
export default {
  name: 'TranlateForm',
  data () {
    return {
        textTranslate:"",
        language:""
    }
  },
  methods:{
    responsetext:function () {
    	this.$emit("responsetext",this.textTranslate,this.language);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
   .TranlateForm{
	   	width: 60%;
	   	margin: 0 auto;
	   	border: 1px lightgray solid;
	   	border-radius: 5px;
	   	background: rgba(0,0,0,.1);
	   	padding: 5px 5px;
   }
   input[type="text"],select{
	   	display: block;
	   	width: 100%;
	   	background: transparent;
	    box-sizing: border-box;
	    outline: none;
   }
   input[type="text"]{
   	    border: none;
	    border-bottom: 1px solid lightgray;
   	    padding: 10px 5px;
   }
   select{
/*   	padding: */
   	    padding: 5px 5px;
   	    border: none;
   	    border-bottom: 1px solid lightgray;
   }
   input[type="submit"]{
	   	background: blue;
	   	border: none;
	   	border-radius: 5px;
	   	padding: 5px 10px;
	   	font-size: 20px;
	   	color: white;
		outline: none;
		cursor: pointer;
	   	margin-top: 10px;
   }
</style>
