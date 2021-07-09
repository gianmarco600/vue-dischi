<template>
  <div id="app">
    <Header @genere="selezionaGenere"/>
    <Main :genereSel="genereSelected"/>
  </div>
</template>

<script>


import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    return{
      genereSelected:''
    }
  },
  methods:{
    selezionaGenere(text){
      this.genereSelected = text;
    }
  }

}
</script>

<style lang="scss">

@import '@/style/general.scss';
@import '@/style/vars.scss';


</style>
