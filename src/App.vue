<template>
  <HeaderApp />
  <main>
    <MainApp />
  </main>
</template>

<script>
import axios from 'axios';
import {store} from './data/store';
import HeaderApp from './components/HeaderApp.vue';
import MainApp from './components/MainApp.vue';
  export default {
    components:{
      HeaderApp,
      MainApp
    },
    data(){
      return{
        store
      }
    },
    methods:{
      getCards(){
        const pag1Url = store.apiUrl + store.page1
        axios.get(pag1Url).then((response) =>{
          store.cardArray = response.data.data;
          console.log(store.cardArray)
        })
      }
      
    },
    created(){
      this.getCards();
    }
  }
</script>

<style lang="scss" scoped>
  main{
    background-color: orange;
  }
</style>