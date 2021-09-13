<template>
  <section class="container">
      <div class="row">
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