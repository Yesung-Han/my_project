<template>
  <div id="app">
    <h1>My Apps!</h1>
    <router-link v-bind:to="{ name: 'HelloWorld' }">Home</router-link>
    <router-link v-bind:to="{ name: 'TodoList'}">Todo</router-link>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
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

h1 {
  text-align: center;
}
</style>
