<template>
  <button @click="textInputValues()" class="spinButton">SPIN THE WHEEL</button>
  {{ bets }}
  <ul v-for="item in randomNumberValues" :key="item">
    <li>Number: {{ item.number }}</li>
    <li>Color: {{ item.color }}</li>
    <li>Is lower number: {{ item.lowerNumber }}</li>
    <li>Is higher number: {{ item.higherNumber }}</li>
    <li>First dozen: {{ item.firstDozen }}</li>
    <li>Second dozen: {{ item.secondDozen }}</li>
    <li>Third dozen: {{ item.thirdDozen }}</li>
    <li>Odd: {{ item.odd }}</li>
    <li>Even: {{ item.even }}</li>
    <li>First column: {{ item.firstColumn }}</li>
    <li>Second column: {{ item.secondColumn }}</li>
    <li>Third column: {{ item.thirdColumn }}</li>
  </ul>
</template>

<script>
import { numbers } from '../../data';

export default {
  name: 'RouletteOutput',
  data() {
    return {
      randomNumberValues: [],
      foo: [],
      /*{*/
      /*         number: null,
        color: null,
        lowerNumber: null,
        higherNumber: null,
        firstDozen: null,
        secondDozen: null,
        thirdDozen: null,
        odd: null,
        even: null,
        firstColumn: null,
        secondColumn: null,
        thirdColumn: null, */
      /* }, */
    };
  },
  props: {
    bets: {
      type: Array,
      required: false,
      default: () => [],
    },
  },
  methods: {
    textInputValues() {
      this.randomNumberValues = [];

      const pickRandomNumberValue = Math.floor(Math.random() * numbers.length);

      this.randomNumberValues.push(numbers[pickRandomNumberValue]);
      this.checkForWin(numbers[pickRandomNumberValue]);
    },
    checkForWin(pickedValues) {
      this.bets.forEach((item) => {
        if (pickedValues.number === item) {
          console.log('NUMBER IST GLEICH');
        }
        if (pickedValues.color === item) {
          console.log('FARBE IST GLEICH');
        }
        if (pickedValues.lowerNumber === item) {
          console.log('LOWER NUMBER IST GLEICH');
        }
        if (pickedValues.higherNumber === item) {
          console.log('HIGHER NUMBER IST GLEICH');
        }
        if (pickedValues.firstDozen === item) {
          console.log('FIRST DOZEN IST GLEICH');
        }
        if (pickedValues.secondDozen === item) {
          console.log('SECOND DOZEN IST GLEICH');
        }
        if (pickedValues.thirdDozen === item) {
          console.log('THIRD DOZEN IST GLEICH');
        }
        if (pickedValues.odd === item) {
          console.log('ODD IST GLEICH');
        }
        if (pickedValues.even === item) {
          console.log('EVEN IST GLEICH');
        }
        if (pickedValues.firstColumn === item) {
          console.log('FIRST COLUMN IST GLEICH');
        }
        if (pickedValues.secondColumn === item) {
          console.log('SECOND COLUMN IST GLEICH');
        }
        if (pickedValues.thirdColumn === item) {
          console.log('THIRD COLUM IST GLEICH');
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
</style>
