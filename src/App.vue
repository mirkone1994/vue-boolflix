<template>
  <div id="app">
    <Header @doSearch="getSearchPadre"/>
    <div class="container-fluid bg-grey">
      <Films :searchQuery="searchQuery" :films="films" :series="series"/>
    </div>
    
  </div>
</template>

<script>
import axios from "axios";
import Header from "./components/Header.vue"
import Films from "./components/Films.vue"
export default {
  name: 'App',
  components: {
    Header,
    Films,
  },
  data(){
    return {
      baseUri : "https://api.themoviedb.org/3",
      apiKey : "a21c1888019d78a2591d2a3dc243bfe1",
      films : [],
      series: [],
      searchQuery: "",
    }
  },
  
  methods:{
    getSearchPadre(search){
      this.searchQuery = search

      axios.get(`${this.baseUri}/search/movie?api_key=${this.apiKey}&query=${this.searchQuery}`).then((res)=>
        {
            this.films=res.data.results;
        }).catch((err)=>{
            console.log(err);
        });

      axios.get(`${this.baseUri}/search/tv?api_key=${this.apiKey}&query=${this.searchQuery}`).then((res)=>
        {
            this.series=res.data.results;
        }).catch((err)=>{
            console.log(err);
        });
    },
  },
}
</script>

<style lang="scss">
@import "scss/style.scss";
@import '~@fortawesome/fontawesome-free/css/all.min.css';

.bg-grey {
  background-color: grey;
}
</style>
