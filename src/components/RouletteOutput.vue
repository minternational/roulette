<template>
  <button class="spinButton">SPIN THE WHEEL</button>
</template>

<script>
export default {
  name: "RouletteOutput"
}
</script>

<style scoped>
  .spinButton {
    margin: 3rem auto;
    font-weight: bold;
    font-size: 1.25rem;
    text-transform: uppercase;
    padding: 1rem;
    display: block;
    border: 1px solid white;
    background-color: black;
    color: white;
    transition: .3s;
  }

  .spinButton:hover {
    background-color: white;
    border: 1px solid black;
    color: black;
    transition: .3s;
    cursor: pointer;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.5)
  }
</style>