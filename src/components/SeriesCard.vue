<template>
  <section class="films-card">
    <div class="container">
      <div class="deck">
        <div class="card hovercard">
          <div class="front face">
            <img class="poster" :src="poster(serie.poster_path)" alt="">
          </div>
          <div class="back face">
            <span>{{serie.name}}</span>
            <span>{{serie.original_name}}</span>
            <img class="flag" v-if="flags.includes(serie.original_language)" :src="flag(serie.original_language)" :alt="serie.title">
            <span v-else>{{serie.original_language}}</span>
            <span class="star" v-for="star in 5" :key="star">
              <i v-if="star<=isWhole(serie.vote_average)" class="fas fa-star"></i>
              <i v-else class="far fa-star"></i>
            </span>
          </div>
        </div>
      </div>
    </div>
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
.deck{
  margin:15px;
  width:341px;
  height:515px;
  position:relative;
  border-radius:10px;
}
.card{
  width:100%;
  height:100%;
  -webkit-transform-style: preserve-3d;
  transform-style: preserve-3d;
  -webkit-transition: all .5s linear;
  transition: all .5s linear;
}
.face {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
  background-color:#fff;  
}
.back {
  overflow:hidden;
  z-index:-1;
  display: block;
  -webkit-transform: rotateY(180deg);
  transform: rotateY(180deg);
}
.front, .back{
  transition: all .5s linear;
}
.front{
  z-index:1;
}
.hovercard:hover{
  -webkit-transform: rotateY(180deg);
  transform: rotateY(180deg);
}
</style>