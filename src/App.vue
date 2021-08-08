<template>
   <zip-details></zip-details>
</template>

<script>

import ZipDetails from './components/ZipDetails.vue';


export default {
  name: 'App',
  components: {
    ZipDetails
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
