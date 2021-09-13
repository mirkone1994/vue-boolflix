vue<template>
  <section class="series-card">
      <img :src="poster(serie.poster_path)" alt="">
      <span>{{serie.name}}</span>
      <span>{{serie.original_name}}</span>
      <img v-if="flags.includes(serie.original_language)" :src="flag(serie.original_language)" :alt="serie.title">
      <span v-else>{{serie.original_language}}</span>
      <span>{{isWhole(serie.vote_average)}}</span>
      <span v-for="star in 5" :key="star"><i class="fas fa-star"></i></span>
  </section>
</template>

<script>
export default {
name: "SeriesCard",
props: ["serie"],
data(){
  return {
    flags: ["en", "it"],
    star: [],
  }
},
methods: {
  flag(lang){
    return require(`@/images/${lang}.png`)
  },
  poster(image){
    return (`https://image.tmdb.org/t/p/w342${image}`)
  },
  isWhole(number){
    return Math.ceil(number/2);
  },

},
}
</script>

<style scoped lang="scss">
span {
    padding-right: 10px;
}
</style>