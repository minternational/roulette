<template>
  <button @click="textInputValues()" class="spinButton">SPIN THE WHEEL</button>
  <span>Bet Amount: <b>{{ betAmount }} €</b></span>
  <br />
  <br />
  <span class="amount">Win Amount: <b>{{ winAmount }} €</b></span>
  <ul v-for="item in randomNumberValues" :key="item">
    <li>Number: <b>{{ item.number }}</b></li>
    <li>Color: <b>{{ item.color }}</b></li>
    <li v-if="item.lowerNumber">Is a lower number</li>
    <li v-if="item.higherNumber">Is a higher number</li>
    <li v-if="item.firstDozen">Belongs to the first dozen</li>
    <li v-if="item.secondDozen">Belongs to the second dozen</li>
    <li v-if="item.thirdDozen">Belongs to the third dozen</li>
    <li v-if="item.odd">Is Odd</li>
    <li v-if="item.even">Is Even</li>
    <li v-if="item.firstColumn">Belongs to the first column</li>
    <li v-if="item.secondColumn">Belongs to the second column</li>
    <li v-if="item.thirdColumn">Belongs to the third column</li>
  </ul>
</template>

<script>
import { numbers } from '../../data';

export default {
  name: 'RouletteOutput',
  data() {
    return {
      randomNumberValues: [],
      winAmount: 0,
    };
  },
  props: {
    bets: {
      type: Array,
      required: false,
      default: () => [],
    },
    betAmount: {
      type: Number,
      required: false,
      default: 0,
    },
  },
  methods: {
    textInputValues() {
      this.randomNumberValues = []
      this. winAmount = 0;

      const pickRandomNumberValue = Math.floor(Math.random() * numbers.length);

      this.randomNumberValues.push(numbers[pickRandomNumberValue]);
      this.checkForWin(numbers[pickRandomNumberValue]);
    },
    checkForWin(pickedValues) {

      this.bets.forEach((item) => {
        if (pickedValues.number === item) {
          this.winAmount = this.betAmount * 35
        }
        if (pickedValues.color === item) {
          this.winAmount = this.betAmount
        }
        if (pickedValues.lowerNumber && item === 'lowerNumber') {
          this.winAmount = this.betAmount
        }
        if (pickedValues.higherNumber && item === 'higherNumber') {
          this.winAmount = this.betAmount
        }
        if (pickedValues.firstDozen && item === 'firstDozen') {
          this.winAmount = this.betAmount * 2
        }
        if (pickedValues.secondDozen && item === 'secondDozen') {
          this.winAmount = this.betAmount * 2
        }
        if (pickedValues.thirdDozen && item === 'thirdDozen') {
          this.winAmount = this.betAmount * 2
        }
        if (pickedValues.odd && item === 'odd') {
          this.winAmount = this.betAmount
        }
        if (pickedValues.even && item === 'even') {
          this.winAmount = this.betAmount
        }
        if (pickedValues.firstColumn && item === 'firstColumn') {
          this.winAmount = this.betAmount * 2
        }
        if (pickedValues.secondColumn && item === 'secondColumn') {
          this.winAmount = this.betAmount * 2
        }
        if (pickedValues.thirdColumn && item === 'thirdColumn') {
          this.winAmount = this.betAmount * 2
        }
      });
    },
  },
};
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
  transition: 0.3s;
}

.spinButton:hover {
  background-color: white;
  border: 1px solid black;
  color: black;
  transition: 0.3s;
  cursor: pointer;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
}

li {
  list-style-type: none;
}

.amount {
  padding-bottom: 4rem;
}
</style>
