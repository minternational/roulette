<template>
  <h1>ROULETTE</h1>
  <RouletteInput />
</template>

<script>
import RouletteInput from './components/RouletteInput.vue';

export default {
  name: 'App',
  components: {
    RouletteInput,
  },
};
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
