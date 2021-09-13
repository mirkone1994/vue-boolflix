<template>
  <section class="films-card">
      <span>{{film.title}}</span>
      <span>{{film.original_title}}</span>
      <img v-if="flags.includes(film.original_language)" :src="flag(film.original_language)" :alt="film.title">
      <span v-else>{{film.original_language}}</span>
      <span>{{film.vote_average}}</span>
  </section>
</template>

<script>
export default {
name: "FilmsCard",
props: ["film"],
data(){
  return {
    flags: ["en", "it"]

  }
},
methods: {
  flag(lang){
    return require(`@/images/${lang}.png`)
  }
 
}
}
</script>

<style scoped lang="scss">
span {
    padding-right: 10px;
}
</style>