<template>
    <div class="container-md">
        <div v-if="load" class="scaffale  gy-5 py-3">
            <div class="rounded _col " v-for="(card,i) in filtraPerGenere" :key="i">
                <Card :disco="card"/>
            </div>
                
        </div>
        <div v-else >
            <Loading/>
        </div>
    </div>
</template>

<script>
import Card from '@/components/Card.vue';
import Loading from '@/components/Loading.vue';
import axios from 'axios';



export default {
    name:'Main',
    components:{
        Card,
        Loading
    },
    data(){
        return{
            apiURL:'https://flynn.boolean.careers/exercises/api/array/music',
            elementList:'',
            load: false,
            
            
        }
    },
    props:['genereSel'],
    created(){
        console.log('creo');
        this.APIcall();
    },
    methods:{
        APIcall(){
            console.log('chiamo');
            axios
            .get(this.apiURL)
            .then(res => {
                this.elementList = res.data.response;
                console.log(this.elementList);
                
            });
            this.load = true;
        }
    },
    computed:{
        filtraPerGenere(){
            if(this.genereSel != ''){
            return this.elementList.filter(elem => {
                elem.genre.toLowerCase() == this.genereSel;
            })
            }
            return this.elementList
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/general.scss';
@import '@/style/vars.scss';

    .scaffale{
        min-width: 100%;
        display: flex;
        flex-wrap: wrap;
        ._col{
            width: calc((100% / 5) - 40px);
            height: 370px;
            padding: 0;
            margin: 40px 20px;
            background-color: $bg-light;
            cursor: pointer;
            &:hover{
                box-shadow: rgba(0, 0, 0, 0.25) 0px 54px 55px, rgba(0, 0, 0, 0.12) 0px -12px 30px, rgba(0, 0, 0, 0.12) 0px 4px 6px, rgba(0, 0, 0, 0.17) 0px 12px 13px, rgba(0, 0, 0, 0.09) 0px -3px 5px;;
            }

        }
        
    }
</style>

// {
//             "poster": "https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg",
//             "title": "New Jersey",
//             "author": "Bon Jovi",
//             "genre": "Rock",
//             "year": "1988"
//         }