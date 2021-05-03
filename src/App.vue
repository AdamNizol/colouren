<template>
  <div id="app">
    <ColourGen/>
  </div>
</template>

<script>
import ColourGen from './components/ColourGen.vue'

export default {
  name: 'App',
  components: {
    ColourGen
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
