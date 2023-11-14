<template>
    <div class="container py-4">
        <div class="row justify-content-between">
            <div class="card-wrapper p-5">
                <div class="card-founded">
                    <span>Found {{ store.cardArray.length }} cards</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { store } from '../data/store';
    export default {
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