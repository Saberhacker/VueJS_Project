<template>
    <h1>{{greeting}} {{name}}</h1>
    <h2 v-text="lastname"></h2>
    <h2 v-html="channel"></h2>
</template>

<script>
export default {
  name: 'App',
  data() {
    return{
      greeting: 'Hello',
      name: 'saber',
      lastname: 'seerat',
      channel: '<b>Lajaward</b>'
    }
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
