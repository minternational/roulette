<template>
  <h1>Roulette</h1>
  <RouletteInput />
  <RouletteOutput />
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import RouletteOutput from './components/RouletteOutput.vue'
import RouletteInput from './components/RouletteInput.vue'

export default {
  name: 'App',
  components: {
    RouletteOutput,
    RouletteInput
  }
}
</script>

<style>
/*#app {*/
/*  font-family: Avenir, Helvetica, Arial, sans-serif;*/
/*  -webkit-font-smoothing: antialiased;*/
/*  -moz-osx-font-smoothing: grayscale;*/
/*  text-align: center;*/
/*  color: #2c3e50;*/
/*  margin-top: 60px;*/
/*}*/
</style>
