<template>


  <div class="grid-container">
    <div class="betField">
      <label class="type">Number</label>
      <input type="text" class="inputText" />
      <small class="info">If you want to bet on more than one number</small>
      <small class="info">separate values with comma.</small>
      <small class="info">E.g.: 1,2,4,5</small>
    </div>


    <div class="betField">
      <label class="type">Red or Black</label>
      <input type="radio" class="radioButton" name="color">
      <label>Red</label>
      <p>
      or
      </p>
      <input type="radio" class="radioButton" name="color">
      <label>Black</label>
      <button @click="resetSelection()">Reset Selection</button>
    </div>


    <div class="betField">
      <label class="type">Even or Odd</label>
      <input type="radio" class="radioButton" name="evenOrOdd">
      <label>Even</label>
      <p>
        or
      </p>
      <input type="radio" class="radioButton" name="evenOrOdd">
      <label>Odd</label>
    </div>


    <div class="betField">
      <label class="type">Lower or Higher</label>
      <input type="radio" class="radioButton" name="lowerOrHigher">
      <label>Lower</label>
      <small class="info">1 - 18</small>
      <p>
        or
      </p>
      <input type="radio" class="radioButton" name="lowerOrHigher">
      <label>Higher</label>
      <small class="info">19 - 36</small>
    </div>


    <div class="betField">
      <label class="type">First, Second or Third Dozen</label>
      <input type="radio" class="radioButton" name="dozen">
      <label>First Dozen</label>
      <small class="info">1 - 12</small>
      <p>
        or
      </p>
      <input type="radio" class="radioButton" name="dozen">
      <label>Second Dozen</label>
      <small class="info">13 - 24</small>
      <p>
        or
      </p>
      <input type="radio" class="radioButton" name="dozen">
      <label>Third Dozen</label>
      <small class="info">25 - 36</small>
    </div>


    <div class="betField">
      <label class="type">First, Second or Third Column</label>
      <input type="radio" class="radioButton" name="column">
      <label>First Column</label>
      <small class="info">1, 4, 7, 10, 13, 16, 19, 22, 25, 28, 31, 34</small>
      <p>
        or
      </p>
      <input type="radio" class="radioButton" name="column">
      <label>Second Column</label>
      <small class="info">2, 5, 8, 11, 14, 17, 20, 23, 26, 29, 32, 35</small>
      <p>
        or
      </p>
      <input type="radio" class="radioButton" name="column">
      <label>Third Column</label>
      <small class="info">3, 6, 9, 12, 15, 18, 21, 24, 27, 30, 33, 36</small>
    </div>
  </div>


</template>

<script>
export default {
  name: "RouletteInput.vue",
  methods: {
    resetSelection() {
      const getButtonValue = document.getElementsByName('color')
      getButtonValue.forEach(item => console.log(item))
    }
  }
}

</script>

<style scoped>

  .grid-container {
    width: 1250px;
    margin: auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 10px;
  }

  .betField {
    min-height: 200px;
    width: 600px;
    margin: 1rem auto;
    padding: 2rem 0;
    border: 1px solid rgba(0, 0, 0, 0.2);
    border-radius: 5px;
    transition: .3s;
  }

  .betField:hover {
    background-color: rgba(0, 0, 0, 0.05);
    transition: .3s;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.25);
    border: 1px solid rgba(0, 0, 0, 0.05);
  }

  .inputText {
    border: 1px solid rgba(0, 0, 0, 0.25);
    padding: 0.5rem;
    border-radius: 5px;
  }

  .type {
    font-weight: bold;
    font-size: 1.25rem;
    text-transform: uppercase;
    margin-bottom: 2rem;
    display: block;
  }

  .radioButton {
    height: 1rem;
    width: 1rem;
    margin-right: 1rem;
  }

  .radioButton:hover {
    cursor: pointer;
  }

  .info {
    display: block;
    color: gray;
    padding-top: 0.5rem;
  }

</style>