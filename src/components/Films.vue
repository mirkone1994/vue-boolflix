<template>
  <section id="films" class="container">
      <div class="row">
          <div class="col" v-for="film in films" :key="film.id"><FilmsCard :film="film"/></div>
      </div>
  </section>
</template>

<script>

import FilmsCard from "../components/FilmsCard.vue"
export default {
    name:"Films",
    props: ["searchQuery", "films"],
    components:{
        FilmsCard,
    },
}
</script>

<style scoped lang="scss">

</style>