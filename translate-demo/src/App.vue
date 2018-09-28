<template>
  <div id="app">
    <header>
      <h1>在线翻译</h1>
      <h4>简单/易用/便捷</h4>
    </header>
    <TranslateForm v-on:responsetext="responsetext"></TranslateForm>
    <TranslateOutput v-bind:translatedtext="responsedtext"></TranslateOutput>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'
import axios from 'axios'

export default {
  name: 'App',
  data(){
    return {
      responsedtext:""
    }
  },
  components: {
    TranslateForm,TranslateOutput
  },
  methods:{
    responsetext:function(val,lan){
      console.log(lan);
      axios.get("https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180903T090213Z.96fc1bc6a2a48f6b.08e72b651de4cadaf9bc3633881641c3e127ca0d&lang="+lan+"&text="+val).then((data)=>{
        console.log(2);
        this.responsedtext=data.data.text[0];
      });
    }
  }
}
</script>

<style>
#app{
  text-align: center;
}
h1{
  margin: 10px;
  color:rgba(0,0,0,.7);
}
h4{
  color: lightgray;
  margin:10px;
}
</style>
