<template>
  <div class="grid-container">
    <div class="betField">
      <label class="type">Bet Amount</label>
      <div class="inputWrapper">
        <input
            type="number"
            class="inputText"
            id="number"
            v-model="betAmount"
        /> €
      </div>
    </div>
    <div class="betField">
      <label class="type">Number</label>
      <div class="inputWrapper">
        <input
          type="text"
          class="inputText"
          id="text"
          v-model="betNumbersValues"
        />
      </div>
      <span class="info"
        >If you want to bet on more than one number separate values with comma.
        Max. 4 numbers possible E.g.: 1,2,4,5</span
      >
    </div>
    <div class="betField">
      <label class="type">Red or Black</label>
      <div class="inputWrapper">
        <input
          type="checkbox"
          class="checkbox"
          value="Red"
          id="red"
          name="color"
          v-model="checkedBetValues"
        />
        <label>Red</label>
      </div>

      <input
        type="checkbox"
        class="checkbox"
        value="Black"
        id="black"
        v-model="checkedBetValues"
      />
      <label>Black</label>
    </div>

    <div class="betField">
      <label class="type">Even or Odd</label>
      <div class="inputWrapper">
        <input
          type="checkbox"
          class="checkbox"
          value="even"
          id="even"
          v-model="checkedBetValues"
        />

        <label>Even</label>
      </div>
      <div class="inputWrapper">
        <input
          type="checkbox"
          class="checkbox"
          value="odd"
          id="odd"
          v-model="checkedBetValues"
        />
        <label>Odd</label>
      </div>
    </div>

    <div class="betField">
      <label class="type">Lower or Higher</label>
      <div class="inputWrapper">
        <input
          type="checkbox"
          class="checkbox"
          value="lowerNumber"
          id="lower"
          v-model="checkedBetValues"
        />
        <label>Lower <span class="info">(1 - 18)</span></label>
      </div>
      <div class="inputWrapper">
        <input
          type="checkbox"
          class="checkbox"
          value="higherNumber"
          id="higher"
          v-model="checkedBetValues"
        />
        <label>Higher <span class="info">(19 - 36)</span></label>
      </div>
    </div>

    <div class="betField">
      <label class="type">First, Second or Third Dozen</label>
      <div class="inputWrapper">
        <input
          type="checkbox"
          class="checkbox"
          value="firstDozen"
          id="firstDozen"
          v-model="checkedBetValues"
        />
        <label>First Dozen <span class="info">(1 - 12)</span></label>
      </div>
      <div class="inputWrapper">
        <input
          type="checkbox"
          class="checkbox"
          value="secondDozen"
          id="secondDozen"
          v-model="checkedBetValues"
        />
        <label>Second Dozen <span class="info">(13 - 24)</span></label>
      </div>
      <div class="inputWrapper">
        <input
          type="checkbox"
          class="checkbox"
          value="thirdDozen"
          id="thirdDozen"
          v-model="checkedBetValues"
        />
        <label>Third Dozen <span class="info">(25 - 36)</span></label>
      </div>
    </div>

    <div class="betField">
      <label class="type">First, Second or Third Column</label>
      <div class="inputWrapper">
        <input
          type="checkbox"
          class="checkbox"
          value="firstColumn"
          id="firstColumn"
          v-model="checkedBetValues"
        />
        <label
          >First Column
          <span class="info"
            >(1, 4, 7, 10, 13, 16, 19, 22, 25, 28, 31, 34)</span
          ></label
        >
      </div>
      <div class="inputWrapper">
        <input
          type="checkbox"
          class="checkbox"
          value="secondColumn"
          id="secondColumn"
          v-model="checkedBetValues"
        />
        <label
          >Second Column
          <span class="info"
            >(2, 5, 8, 11, 14, 17, 20, 23, 26, 29, 32, 35)</span
          ></label
        >
      </div>
      <div class="inputWrapper">
        <input
          type="checkbox"
          class="checkbox"
          value="thirdColumn"
          id="thirdColumn"
          v-model="checkedBetValues"
        />
        <label
          >Third Column
          <span class="info"
            >(3, 6, 9, 12, 15, 18, 21, 24, 27, 30, 33, 36)</span
          ></label
        >
      </div>
    </div>
  </div>
  <RouletteOutput :bets="checkedBetValues" :bet-amount="betAmount" />
</template>

<script>
import RouletteOutput from './RouletteOutput.vue';

export default {
  name: 'RouletteInput.vue',
  components: { RouletteOutput },
  data() {
    return {
      checkedBetValues: [],
      betNumbersValues: '',
      betAmount: 0,
    };
  },
  methods: {
    textInputValues() {
      if (this.betNumbersValues !== '') {
        this.checkedBetValues.push(this.betNumbersValues.split(','));
      }
    },
  },
};
</script>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: auto auto;
  grid-gap: 24px;
}

.betField {
  width: 475px;
  padding: 1rem;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 5px;
  transition: 0.3s;
}

.betField:hover {
  background-color: rgba(0, 0, 0, 0.05);
  transition: 0.3s;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.25);
  border: 1px solid rgba(0, 0, 0, 0.05);
}

.inputText {
  border: 1px solid rgba(0, 0, 0, 0.25);
  padding: 0.5rem;
  border-radius: 5px;
  text-align: center;
}

.type {
  font-weight: bold;
  font-size: 1.25rem;
  text-transform: uppercase;
  margin-bottom: 2rem;
  display: block;
}

.checkbox {
  height: 1rem;
  width: 1rem;
  margin-right: 1rem;
}

.checkbox:hover {
  cursor: pointer;
}
.info {
  color: gray;
  font-size: 0.8rem;
}

.inputWrapper {
  display: block;
  margin: 2rem;
}
</style>
