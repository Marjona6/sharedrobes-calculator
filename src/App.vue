<template>
  <div class="flex">
    <img src="./assets/SharedrobesCalculator.webp" />
    <div class="page-title">
      <h1>Rental</h1>
      <h1 class="highlighted">Price</h1>
      <h1>Calculator</h1>
    </div>
  </div>
  <CalculatorInfo />
  <Calculator />
  <CalculationsGuide />
</template>

<script lang="ts">
import CalculatorInfo from './components/CalculatorInfo.vue'
import Calculator from './components/Calculator.vue'
import CalculationsGuide from './components/CalculationsGuide.vue'

export default {
  name: 'App',
  components: {
    CalculatorInfo,
    Calculator,
    CalculationsGuide
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
img {
  width: fit-content;
}
.flex {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
.page-title {
  display: flex;
  flex-direction: column;
}
h1 {
  text-transform: uppercase;
}
.highlighted {
  color: #5dbdbf;
}
</style>
