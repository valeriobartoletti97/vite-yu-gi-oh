<template>
  <HeaderApp/>
  <main>
    <SelectArchetype class="mb-3" @filter="setParams"/>
    <MainApp />
  </main>
</template>

<script>
import axios from 'axios';
import {store} from './data/store';
import HeaderApp from './components/HeaderApp.vue';
import MainApp from './components/MainApp.vue';
import CardComponent from './components/CardComponent.vue';
import SelectArchetype from './components/SelectArchetype.vue';

  export default {
    components:{
    HeaderApp,
    MainApp,
    CardComponent,
    SelectArchetype, 
},
    data(){
      return{
        store,
        params: null
      }
    },
    methods:{
      setParams(search){
         if(search){
          this.params = {
            archetype: search,
            num: 20,
            offset: 0
          }
         }else{
            this.params = null
         }
         this.filterCards();
      },
      getCards(){
        const pag1Url = store.apiUrl + store.page1
        axios.get(pag1Url).then((response) =>{
          store.cardArray = response.data.data;
          console.log(store.cardArray)
        }).catch((error)=>{
          this.store.error = error.message
        }).finally(()=>{
          store.loading = false
        })
      },
      filterCards(){
        const newArchetype = store.apiUrl + "?";
        axios.get(newArchetype, {params : this.params}).then((response) =>{
          store.cardArray = response.data.data
          /* console.log(response.data.data) */
        }).catch((error)=>{
          this.store.error = error.message
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