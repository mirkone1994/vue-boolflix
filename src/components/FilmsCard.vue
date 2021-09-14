<template>
  <section class="films-card">
      <img :src="poster(film.poster_path)" alt="">
      <span>{{film.title}}</span>
      <span>{{film.original_title}}</span>
      <img class="flag" v-if="flags.includes(film.original_language)" :src="flag(film.original_language)" :alt="film.title">
      <span v-else>{{film.original_language}}</span>
      <span class="star" v-for="star in 5" :key="star">
        <i v-if="star<=isWhole(film.vote_average)" class="fas fa-star"></i>
        <i v-else class="far fa-star"></i>
      </span>
  </section>
</template>

<script>
export default {
name: "FilmsCard",
props: ["film"],
data(){
  return {
    flags: ["en", "it"],

  }
},
methods: {
  flag(lang){
    return require(`@/images/${lang}.png`)
  },
  poster(image){
    if (this.film.poster_path) return (`https://image.tmdb.org/t/p/w342${image}`);
    return "https://www.altavod.com/assets/images/poster-placeholder.png"
  },
  isWhole(number){
    return Math.ceil(number/2)
  }
 
}
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