<template>
  <section>
      <input v-model="search" type="text" placeholder="Cerca il film...">
      <button type="button" @click="$emit('doSearch', search)">Cerca</button>
  </section>
</template>

<script>
export default {
name:"Search",
data(){
  return {
    search: "",
  }
}
}
</script>

<style>

</style>