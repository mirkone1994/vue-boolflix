<template>
  <section></section>
</template>

<script>
import axios from "axios";
export default {
    name:"Films",
    data(){
        return {
            baseUri : "https://api.themoviedb.org/3",
            apiKey : "a21c1888019d78a2591d2a3dc243bfe1",
            query : "pinocchio",
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

<style>

</style>