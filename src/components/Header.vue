<template>
  <section class="container-fluid">
      <div class="row justify-content-between align-items-center">
          <div class="col-1">
              <span>BOOLFLIX</span>
          </div>
          <div class="col-8 col-sm-4 col-md-4 col-lg-3 d-flex justify-content-end">
              <input v-model="searchTerm" type="text" placeholder="Cerca il film...">
              <button type="button" @click="$emit('doSearch', searchTerm)"><i class="fas fa-search"></i></button>
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
    background: rgb(0,0,0);
    background: linear-gradient(180deg, rgba(0,0,0,1) 0%, rgba(20,20,22,1) 65%);
}

.row{
    height: 100%;
}
span {
    color: red;
    font-size: 1.5em;
}
i {
    color: #fff;
}
input {
    border-radius: 15px;
}
button {
    background-color: transparent;
    border: none;
}

</style>