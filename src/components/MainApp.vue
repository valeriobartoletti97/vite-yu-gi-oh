<template>
    <LoaderComponent v-if="store.loading"/>
    <div class="container py-4" v-if="store.cardArray.length >= 20">
        <div class="row justify-content-between card-wrapper p-5">
            <div class="card-founded">
                <span>Found {{ store.cardArray.length }} cards</span>
            </div>
            <div class="col-sm-6 col-md-3 col-12 text-center py-3" v-for="(card,index) in store.cardArray" :key="index">
                <CardComponent :img="card.card_images[0].image_url" :title="card.name" :type="card.type" />
            </div>
        </div>
    </div>
    <div class="alert alert-danger text-uppercase text-center" v-if="store.error">
        {{ store.error }}
    </div>
</template>

<script>
import { store } from '../data/store';
import CardComponent from './CardComponent.vue';
import LoaderComponent from './LoaderComponent.vue';
    export default {
        name:'MainApp',
        components:{
    CardComponent,
    LoaderComponent
},
        data(){
            return{
                store
            }
        },
    }
</script>

<style lang="scss" scoped>
     .card-founded{
        background-color:black;
        color:white;
        width: calc(100% - 20px);
        padding:10px;
        margin:auto;
        span{
            font-size: 1.2em;
            font-weight: bold;
        }
     }
     .card-wrapper{
        background-color:white
     }
     h3{
        font-size: 3em;
        font-weight: bolder;
     }
     .loading{
        height: calc(100vh - 76px)
     }
     .col-3.text-center{
        padding: 20px 10 !important
     }
     div.alert-danger{
        width:50%;
        margin: 0 auto;
        background-color: rgb(238, 53, 53);
        font-weight: bolder
     }
</style>