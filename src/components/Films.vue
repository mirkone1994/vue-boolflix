<template>
  <section id="films" class="container">
      <div class="row justify-content-around">
          <div class="col-6 col-xl-4 my-5" v-for="film in films" :key="film.id"><FilmsCard :film="film"/></div>
          <div class="col-6 col-xl-4 my-5" v-for="serie in series" :key="serie.id"><SeriesCard :serie="serie"/></div>
      </div>
  </section>
</template>

<script>

import FilmsCard from "../components/FilmsCard.vue"
import SeriesCard from "../components/SeriesCard.vue"
export default {
    name:"Films",
    props: ["searchQuery", "films", "series"],
    components:{
        FilmsCard,
        SeriesCard,
    },
}
</script>

<style scoped lang="scss">

</style>