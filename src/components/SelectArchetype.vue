<template>
    <select class="form-select" aria-label="Default select example">
      <option selected>Choose Archetype</option>
      <option value="-eyes dragon">-Eyes Dragon</option>
      <option value="advanced-crystal-beast">Advanced Crystal Beast</option>
      <option value="amazoness">Amazoness</option>
      <option value="ancient-gear">Ancient Gear</option>
      <option value="blue-eyes">Blue-Eyes</option>
    </select>
</template>

<script>
    export default {
        name: 'SelectArchetype',

    }
</script>

<style lang="scss" scoped>
    select{
        width: calc(100% - 20px);
        padding: 20px 10 !important;
        margin:auto
    }
</style>