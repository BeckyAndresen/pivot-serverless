<template>
  <div id='app'>
    <CreateElection/>
  </div>
</template>

<script>
import CreateElection from './components/CreateElection.vue'

export default {
  name: 'App',
  components: {
    CreateElection
  },
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
