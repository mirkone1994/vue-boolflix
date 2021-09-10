<template>
  <section class="films-card">
      <span>{{film.title}}</span>
      <span>{{film.original_title}}</span>
      <span>{{film.original_language}}</span>
      <span>{{film.vote_average}}</span>
  </section>
</template>

<script>
export default {
name: "FilmsCard",
props: ["film"]
}
</script>

<style scoped lang="scss">
span {
    padding-right: 10px;
}
</style>