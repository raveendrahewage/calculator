<template>
  <v-card title="CALCULATOR" class="mx-auto" width="400">
    <v-sheet elevation="12" max-width="600" rounded="lg" width="100%" class="sheet pa-4 text-center mx-auto">
      <v-form @submit.prevent>
        <v-row no-gutters>
          <v-text-field v-model="input" type="text" variant="outlined" class="input-field"></v-text-field>
        </v-row>
        <v-row>
          <v-col cols="12" sm="2">
            <v-btn @click="onClick('x2')" color="deep-orange-darken-3" size="small" block :active="inOperation === 'x2'"
              class="operation-btn-top">x<sup>2</sup></v-btn>
          </v-col>
          <v-col cols="12" sm="2">
            <v-btn @click="onClick('x3')" color="deep-orange-darken-3" size="small" block :active="inOperation === 'x3'"
              class="operation-btn-top">x<sup>3</sup></v-btn>
          </v-col>
          <v-col cols="12" sm="2">
            <v-btn @click="onClick('xy')" color="deep-orange-darken-3" size="small" block :active="inOperation === 'xy'"
              class="operation-btn-top">x<sup>y</sup></v-btn>
          </v-col>
          <v-col cols="12" sm="2">
            <v-btn @click="onClick('10x')" color="deep-orange-darken-3" size="small" block :active="inOperation === '10x'"
              class="operation-btn-top">10<sup>x</sup></v-btn>
          </v-col>
          <v-col cols="12" sm="2">
            <v-btn @click="onClick('x!')" color="deep-orange-darken-3" size="small" block :active="inOperation === 'x!'"
              class="operation-btn-top">x!</v-btn>
          </v-col>
          <v-col cols="12" sm="2">
            <v-btn @click="onClick('1/x')" color="deep-orange-darken-3" size="small" block :active="inOperation === '1/x'"
              class="operation-btn-top">1/x</v-btn>
          </v-col>
          <v-col cols="12" sm="2">
            <v-btn @click="onClick('sin')" color="deep-orange-darken-3" size="small" block :active="inOperation === 'sin'"
              class="operation-btn-top">sin</v-btn>
          </v-col>
          <v-col cols="12" sm="2">
            <v-btn @click="onClick('cos')" color="deep-orange-darken-3" size="small" block :active="inOperation === 'cos'"
              class="operation-btn-top">cos</v-btn>
          </v-col>
          <v-col cols="12" sm="2">
            <v-btn @click="onClick('tan')" color="deep-orange-darken-3" size="small" block :active="inOperation === 'tan'"
              class="operation-btn-top">tan</v-btn>
          </v-col>
          <v-col cols="12" sm="2">
            <v-btn @click="onClick('log2')" color="deep-orange-darken-3" size="small" block
              :active="inOperation === 'log2'" class="operation-btn-top">log<sub>2</sub></v-btn>
          </v-col>
          <v-col cols="12" sm="2">
            <v-btn @click="onClick('log10')" color="deep-orange-darken-3" size="small" block
              :active="inOperation === 'log10'" class="operation-btn-top">log<sub>10</sub></v-btn>
          </v-col>
          <v-col cols="12" sm="2">
            <v-btn @click="onClick('2√x')" color="deep-orange-darken-3" size="small" block :active="inOperation === '2√x'"
              class="operation-btn-top"><sup>2</sup>√x</v-btn>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('AC')" color="grey-lighten-3" size="x-large" block>AC</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('+/-')" color="grey-lighten-3" size="x-large" block>+/-</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('%')" color="grey-lighten-3" size="x-large" block>%</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('÷')" color="warning" size="x-large" block :active="inOperation === '÷'"
              class="operation-btn">÷</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('7')" color="grey-lighten-3" size="x-large" block>7</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('8')" color="grey-lighten-3" size="x-large" block>8</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('9')" color="grey-lighten-3" size="x-large" block>9</v-btn>
          </v-col>
          <v-col cols="12" sm="3">

            <v-btn @click="onClick('×')" color="warning" size="x-large" block :active="inOperation === '×'"
              class="operation-btn">×</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('4')" color="grey-lighten-3" size="x-large" block>4</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('5')" color="grey-lighten-3" size="x-large" block>5</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('6')" color="grey-lighten-3" size="x-large" block>6</v-btn>
          </v-col>
          <v-col cols="12" sm="3">

            <v-btn @click="onClick('-')" color="warning" size="x-large" block :active="inOperation === '×'"
              class="operation-btn">-</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('1')" color="grey-lighten-3" size="x-large" block>1</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('2')" color="grey-lighten-3" size="x-large" block>2</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('3')" color="grey-lighten-3" size="x-large" block>3</v-btn>
          </v-col>
          <v-col cols="12" sm="3">

            <v-btn @click="onClick('+')" color="warning" size="x-large" block :active="inOperation === '+'"
              class="operation-btn">+</v-btn>
          </v-col>
          <v-col cols="12" sm="6">
            <v-btn @click="onClick('0')" color="grey-lighten-3" size="x-large" block>0</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('.')" color="grey-lighten-3" size="x-large" block>.</v-btn>
          </v-col>
          <v-col cols="12" sm="3">
            <v-btn @click="onClick('=')" type="submit" color="indigo-darken-4" size="x-large" block
              class="submit-btn">=</v-btn>
          </v-col>
        </v-row>
      </v-form>
    </v-sheet>
  </v-card>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'CalculatorComponent',
  data(): {
    input: string;
    lastAnswer: number;
    inOperation: string | null;
    evaluation: string[];
  } {
    return {
      input: '',
      lastAnswer: 0,
      inOperation: null,
      evaluation: []
    }
  },
  methods: {
    onClick(value: string) {
      switch (value) {
        case "AC":
          this.input = "";
          this.lastAnswer = 0;
          this.evaluation = [];
          break;
        case "+/-":
          this.input = ((+this.input) * (-1)).toString();
          break;
        case "%":
          this.input = ((+this.input) / 100).toString();
          break;
        case ".":
          this.input = this.input.includes(".") ? this.input : this.input + value;
          break;
        case "x2":
          this.input = Math.pow(+this.input, 2).toString();
          break;
        case "x3":
          this.input = Math.pow(+this.input, 3).toString();
          break;
        case "10x":
          this.input = Math.pow(10, +this.input).toString();
          break;
        case "1/x":
          this.input = (1 / (+this.input)).toString();
          break;
        case "x!":
          this.input = this.factorialize(+this.input).toString();
          break
        case "sin":
          this.input = (Math.sin((+this.input / 180) * Math.PI)).toString();
          break
        case "cos":
          this.input = (Math.cos((+this.input / 180) * Math.PI)).toString();
          break
        case "tan":
          this.input = (Math.tan((+this.input / 180) * Math.PI)).toString();
          break
        case "log2":
          this.input = Math.log2(+this.input).toString();
          break
        case "log10":
          this.input = Math.log10(+this.input).toString();
          break;
        case "2√x":
          this.input = Math.sqrt(+this.input).toString();
          break;
        case "0":
        case "1":
        case "2":
        case "3":
        case "4":
        case "5":
        case "6":
        case "7":
        case "8":
        case "9":
          this.input = this.inOperation ? value : +this.input > 0 ? this.input + value : value;
          this.lastAnswer = this.calculate();
          this.inOperation = null;
          break;
        case "=":
          this.lastAnswer = this.calculate();
          this.input = this.lastAnswer.toString();
          this.evaluation = [];
          this.inOperation = null;
          break;
        default:
          if (+this.input > 0) {
            this.inOperation = value;
            this.evaluation = [];
            this.evaluation.push(this.lastAnswer > 0 ? this.lastAnswer.toString() : this.input);
            this.evaluation.push(value);
            this.input = this.evaluation[0];
          }
          break;
      }
    },
    calculate(): number {
      switch (this.evaluation[1]) {
        case "÷":
          return (+this.evaluation[0]) / (+this.input);
        case "×":
          return (+this.evaluation[0]) * (+this.input);
        case "-":
          return (+this.evaluation[0]) - (+this.input);
        case "+":
          return (+this.evaluation[0]) + (+this.input);
        case "xy":
          return Math.pow(+this.evaluation[0], +this.input);
        default:
          return +this.input;
      }
    },
    factorialize(num: number): number {
      if (num < 0)
        return -1;
      else if (num == 0)
        return 1;
      else {
        return (num * this.factorialize(num - 1));
      }
    }
  }
});
</script>

<style scoped>
.operation-btn,
.submit-btn {
  font-size: 30px;
}

.operation-btn-top {
  font-size: 10px;
}

.input-field>>>input {
  text-align: right;
  font-size: 30px;
  border-radius: 5px;
}
</style>
