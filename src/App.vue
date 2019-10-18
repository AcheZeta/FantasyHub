<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
export default {
  name: 'app',
  components: {}
}
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Nunito&display=swap");
#app {
  font-family: Nunito;
  color: #2c3e50;
  margin: 0;
  padding: 0;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
