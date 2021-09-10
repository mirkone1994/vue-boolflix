<template>
  <section class="container">
      <div class="row">
          <div class="col-3">
              <span>BOOLFLIX</span>
          </div>
          <div class="col-3">
              <Search @doSearch="search"/>

          </div>
      </div>

  </section>
</template>

<script>
import Search from "../components/Search.vue"
export default {
    name:"Header",
    data(){
        return{
            searchTerm: "",
        }
    },
    components: {
        Search,
    },
    methods: {
        search(text){
            this.searchTerm = text;
        }
    }

}
</script>

<style scoped lang="scss">
.container {
    max-width: 1400px;
    margin: auto;
    background-color: #000;
}
.row {
    display: flex;
    justify-content: space-around;
}
span {
    color: red;
}

</style>