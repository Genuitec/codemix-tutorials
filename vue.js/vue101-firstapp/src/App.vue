<template>
  <div id="app">
    <StarWarsPeople></StarWarsPeople>
  </div>
</template>

<script>
import StarWarsPeople from "./components/StarWarsPeople";

export default {
  name: 'app',
  components: {
    StarWarsPeople
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
