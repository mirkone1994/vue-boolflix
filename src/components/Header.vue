<template>
  <section class="container-fluid">
      <div class="row justify-content-around align-items-center">
          <div class="col-1">
              <span>BOOLFLIX</span>
          </div>
          <div class="col-2">
              <input v-model="searchTerm" type="text" placeholder="Cerca il film...">
              <button type="button" @click="$emit('doSearch', searchTerm)">Cerca</button>
          </div>
      </div>

  </section>
</template>

<script>
export default {
    name:"Header",
    data(){
        return{
            searchTerm: "",
        }
    },
}
</script>

<style scoped lang="scss">
.container-fluid {
    height: 75px;
    background-color: #000;
}
.row{
    height: 100%;
}
span {
    color: red;
    font-size: 2em;
}

</style>