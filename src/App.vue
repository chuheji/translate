<template>
  <div id="app">
    <h1>在线翻译</h1>
    <h5>简单 / 易用 / 便捷</h5>
    <Needtranslate @submitform='translateText'></Needtranslate>
    <Translated v-text='translatedText'></Translated>
  </div>
</template>

<script>
import Needtranslate from './components/needtranslate'
import Translated from './components/translated'

export default {
  name: 'App',
  data(){
    return {
      translatedText: ''
    }
  },
  components: {
    Needtranslate,
    Translated
  },
  methods: {
    translateText(text,language){
      // alert(text)
      this.$axios.get('https://translate.yandex.net/api/v1.5/tr.json/translate',{
        params: {
          key: 'trnsl.1.1.20190226T064355Z.becbe581967801e0.738e342f08091b6f0dd9879e1d6195bee469394c',
          lang: language,
          text: text
        }
      })
      .then(res=>{
        this.translatedText = res.data.text[0]
        // console.log(this.translatedText[0])
      })
    }
  }
}
</script>

<style>
  #app{
    position: absolute;
    top: 50%;
    left: 50%;
    transform:translate(-50%,-50%);
    font-family: Helvetica, Tahoma, Arial, "PingFang SC", "Hiragino Sans GB", "Heiti SC", "Microsoft YaHei", "WenQuanYi Micro Hei", sans-serif;
  }
  h5{
    color: #666;
  }
</style>
