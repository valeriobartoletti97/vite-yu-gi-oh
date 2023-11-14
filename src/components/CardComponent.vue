<template>
    <div class="img-card-container">
            <img :src="img" :alt="title">
    </div>
    <div class="card-description py-4">
        <h5 class="text-uppercase">{{title}}</h5>
        <div>{{type}}</div>
    </div>
</template>

<script>
    export default {
        name:'CardComponent',
        props:{
            img:String,
            title:String,
            type:String
        }
    }
</script>

<style lang="scss" scoped>
     .img-card-container{
        width:100%;
        overflow:hidden;
        img{
            width:100%
        }
     }
     .card-description{
            background-color:orange;
            h5{
                color:white
            }
            height: 120px
        }
</style>