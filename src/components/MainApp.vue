<template>
    <div class="container py-4">
        <div class="row justify-content-between card-wrapper p-5">
            <div class="card-founded">
                <span>Found {{ store.cardArray.length }} cards</span>
            </div>
            <div class="col-3 text-center py-3" v-for="(card,index) in store.cardArray" :key="index">
                <CardComponent :img="card.card_images[0].image_url" :title="card.name" :type="card.type" />
            </div>
        </div>
    </div>
</template>

<script>
import { store } from '../data/store';
import CardComponent from './CardComponent.vue';
    export default {
        name:'MainApp',
        components:{
    CardComponent,
},
        data(){
            return{
                store
            }
        }
    }
</script>

<style lang="scss" scoped>
     .card-founded{
        background-color:black;
        color:white;
        padding:10px;
        span{
            font-size: 1.2em;
            font-weight: bold;
        }
     }
     .card-wrapper{
        background-color:white
     }
</style>