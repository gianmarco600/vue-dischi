<template>
    <div class="loadingBox ">
        <h2>loading...</h2>
    </div>
</template>

<script>
export default {
    name:'Loading'
}
</script>

<style lang="scss" scoped>
@import '@/style/general.scss';
@import '@/style/vars.scss';

.loadingBox{
    position: fixed;
    transform: translate(-50%, -50%);
    top: 50%;
    left: 50%;
    h2{
        text-transform: uppercase;
        font-size: 50px;
        color: white;
    }
}
</style>