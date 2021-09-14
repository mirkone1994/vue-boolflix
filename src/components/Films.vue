<template>
  <section id="films" class="container">
      <div class="row justify-content-between">
          <h2>Film</h2>
          <div class="col-12 col-md-6 col-lg-5 col-xl-4 my-5" v-for="film in films" :key="film.id"><FilmsCard :film="film"/></div>
          <h2>TV-Shows</h2>
          <div class="col-12 col-md-6 col-lg-5 col-xl-4 my-5" v-for="serie in series" :key="serie.id"><SeriesCard :serie="serie"/></div>
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
h2{
    color: #fff;
}

</style>