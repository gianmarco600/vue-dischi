<template>
  <div class="_card">
      <img class="_cover " :src="disco.poster" alt="">
      <div class="info">
            <h3>{{disco.title}}</h3>
            <h4>{{disco.author}}</h4>
            <h5>{{disco.year}}</h5>
      </div>
      
  </div>
</template>

<script>
export default {
    name:"Card",
    props:['disco'],
    data(){
        return{

        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/general.scss';
@import '@/style/vars.scss';

._card{
    width: 100%;
    height: 100%;
    position: relative;
    padding: 10px;
    ._cover{
         width: 100%;
    }
    .info{
        position: absolute;
        width: 100%;
        bottom: 15px;
        left: 50%;
        transform: translate(-50% , 0);
        h3{
            color: white;
            text-align: center;
            font-size: 20px;
            margin-top: 15px;
        }
        h4{
            color: white;
            text-align: center;
            font-size: 20px;
            margin-top: 15px;
        }
        h5{
            color: white;
            text-align: center;
            font-size: 12px;
            margin-top: 5px;
        }
    }
}
</style>