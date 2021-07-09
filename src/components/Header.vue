<template>
    <header > 
        <div class="container-md">
            <img class="flo_l" src="@/assets/Spotify.png" alt="">
            
            <select class="flo_r" v-on:change="$emit('genere' ,filtroGenere )"  v-model='filtroGenere' name="cars" id="cars">
                <option value="">none</option>
                <option value="rock">rock</option>
                <option value="pop">pop</option>
                <option value="jazz">jazz</option>
                <option value="metal">metal</option>
            </select>

        </div> 
    </header>
</template>

<script>
export default {
    name: "Header",
    data(){
        return{
            filtroGenere:''
        }
    } ,
    methods:{
        // filtro(){
        //     // console.log(this.filtroGenere)
        //     return this.$emit('genere' , this.filtroGenere )
        // }
    },
}
</script>

<style lang="scss" scoped>
    @import 'bootstrap';
    @import '@/style/vars.scss';
    header{
        background-color: $bg-light;
        width: 100%;
        height: 50px;
        div{
            .flo_l{
                float: left;
                margin-top: 5px;
                margin-left: 10px;
                height: 40px;
            }
            .flo_r{
                float: right;
            }
        }
        
    }
</style>