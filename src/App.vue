<template>
  <div id="app">
    <Header/>
    <Films/>
  </div>
</template>

<script>
import Header from "./components/Header.vue"
import Films from "./components/Films.vue"
export default {
  name: 'App',
  components: {
    Header,
    Films,
    
  }
}
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
