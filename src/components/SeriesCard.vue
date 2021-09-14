<template>
  <section class="series-card">
      <img class="poster" :src="poster(serie.poster_path)" alt="">
      <span>{{serie.name}}</span>
      <span>{{serie.original_name}}</span>
      <img class="flag" v-if="flags.includes(serie.original_language)" :src="flag(serie.original_language)" :alt="serie.title">
      <span v-else>{{serie.original_language}}</span>
      <span class="star" v-for="star in 5" :key="star">
        <i v-if="star<=isWhole(serie.vote_average)" class="fas fa-star"></i>
        <i v-else class="far fa-star"></i>
      </span>
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
    if (this.serie.poster_path) return (`https://image.tmdb.org/t/p/w342${image}`)
    return "https://www.altavod.com/assets/images/poster-placeholder.png"
  },
  isWhole(number){
    return Math.ceil(number/2);
  },

},
}
</script>

<style scoped lang="scss">
.flag {
  height: 20px;
}
span {
  display: block;
}
.star {
  display: inline-block;
}
</style>