<template>
  <v-container fill-height fluid>
    <Calculator />
  </v-container>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Calculator from './components/CalculatorComponent.vue';

export default defineComponent({
  name: 'App',
  components: {
    Calculator
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

html {
  width: 100%;
  height: 100%;
  background-color: #154c79;
  background-image: url("./assets/bg.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}
</style>
