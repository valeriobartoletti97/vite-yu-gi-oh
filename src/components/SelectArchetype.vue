<template>
    <select class="form-select" id="select" v-model="filteredArchetype" @change="sendData">
      <option value="Blackwing">Blackwing</option>
      <option value="Cyber Dragon">Cyber Dragon</option>
      <option selected value="Amazoness">Amazoness</option>
      <option value="Ancient Gear">Ancient Gear</option>
      <option value="Blue-Eyes">Blue-Eyes</option>
    </select>
</template>

<script>
    export default {
        name: 'SelectArchetype',
        data(){
            return{
                filteredArchetype :'',
            }
        },
        methods:{
            sendData(){
                this.$emit('filter', this.filteredArchetype)
            }
        }
    }
</script>

<style lang="scss" scoped>
    select{
        width: 30%;
        margin: 0 auto;
    }
</style>