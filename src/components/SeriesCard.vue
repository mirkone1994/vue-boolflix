vue<template>
  <section class="series-card">
      <span>{{serie.name}}</span>
      <span>{{serie.original_name}}</span>
      <span>{{serie.original_language}}</span>
      <span>{{serie.vote_average}}</span>
  </section>
</template>

<script>
export default {
name: "SeriesCard",
props: ["serie"],
data(){
  return {

  }
},
method: {
 
}
}
</script>

<style scoped lang="scss">
span {
    padding-right: 10px;
}
</style>