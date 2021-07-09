<template>
  <div id="app">
    <Header @genere="genereSelected"/>
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
  }

}
</script>

<style lang="scss">

@import '@/style/general.scss';
@import '@/style/vars.scss';


</style>
