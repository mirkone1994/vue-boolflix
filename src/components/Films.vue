<template>
  <section id="films" class="container">
      <div class="row">
          <div class="col" v-for="film in films" :key="film.id"><FilmsCard :film="film"/></div>
      </div>
  </section>
</template>

<script>
import axios from "axios";
import FilmsCard from "../components/FilmsCard.vue"
export default {
    name:"Films",
    components:{
        FilmsCard,
    },
    data(){
        return {
            baseUri : "https://api.themoviedb.org/3",
            apiKey : "a21c1888019d78a2591d2a3dc243bfe1",
            query : "anelli",
            films : [],
        }
    },
    created(){
        axios.get(`${this.baseUri}/search/movie?api_key=${this.apiKey}&query=${this.query}`).then((res)=>
        {
            this.films=res.data.results;
        }).catch((err)=>{
            console.log(err);
        });
    }
}
</script>

<style scoped lang="scss">

</style>