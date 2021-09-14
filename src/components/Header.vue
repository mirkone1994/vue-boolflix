<template>
  <section class="container-fluid">
      <div class="row justify-content-around">
          <div class="col-3">
              <span>BOOLFLIX</span>
          </div>
          <div class="col-3">
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
    background-color: #000;
}
.row {
}
span {
    color: red;
}

</style>