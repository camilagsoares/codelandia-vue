<template>
  <div>
    <TheHeader />
    <TheNoticias />
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheNoticias from "./components/TheNoticias.vue"

export default {
  name: 'App',
  components: {
    TheHeader,
    TheNoticias
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
