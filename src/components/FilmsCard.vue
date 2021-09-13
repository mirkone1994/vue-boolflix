<template>
  <section class="films-card">
      <span>{{film.title}}</span>
      <span>{{film.original_title}}</span>
      <span v-if="lang"><img src="../images/en.png" alt=""></span>
      <span>{{film.vote_average}}</span>
  </section>
</template>

<script>
export default {
name: "FilmsCard",
props: ["film"],
data(){
  return {
    lang: "",
  }
},
method: {
  isLang(){
    if (this.film.original == "en"){
      this.lang == "en"
    } else this.lang == "it"
  }
}
}
</script>

<style scoped lang="scss">
span {
    padding-right: 10px;
}
</style>