<template>
    <header > 
        <div class="container-md">
            <img class="flo" src="@/assets/Spotify.png" alt="">
        </div> 
    </header>
</template>

<script>
export default {
    name: "Header"
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
            .flo{
                float: left;
                margin-top: 5px;
                margin-left: 10px;
                height: 40px;
            }
        }
        
    }
</style>