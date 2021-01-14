<template>
  <h1>Rental Price Calculator</h1>
  <p>At Sharedrobes, we recommend that your daily rental price is:</p>
  <ul>
    <li>
      2.0% of the RRP (Recommended Retail Price) of your item if your Minimum
      Rental Period is One week (7 days),
    </li>
    <li>1.75% if it's Two weeks (14 days),</li>
    <li>1.5% if it's Three weeks (21 days), and</li>
    <li>1.25% if it's One month (30 days).</li>
  </ul>
  <p>
    The minimum daily rental price is €1.50 for all items. Considering our
    recommended minimum rental period of 7 days, that translates into a minimum
    of at least €10.50 per booking.
  </p>
  <p class="cta">
    Enter your options below, and we'll calculate a daily rental price for your
    item, together with telling you in approximately how many bookings you will
    have paid your item's RRP:
  </p>
  <Calculator />
  <p>To calculate the Rental Daily Price on your own:</p>
  <ul>
    <li>
      <p>For One week (7 days)</p>
      <ul>
        <li>RRP * 2.0% + ((Cleaning (or Repairing) Cost) / 7).</li>
      </ul>
    </li>
    <li>
      <p>For Two weeks (14 days)</p>
      <ul>
        <li>RRP * 1.75% + ((Cleaning (or Repairing) Cost) / 14).</li>
      </ul>
    </li>
    <li>
      <p>For Three weeks (21 days)</p>
      <ul>
        <li>RRP * 1.5% + ((Cleaning (or Repairing) Cost) / 21).</li>
      </ul>
    </li>
    <li>
      <p>For One Month (30 days)</p>
      <ul>
        <li>RRP * 1.25% + ((Cleaning (or Repairing) Cost) / 30).</li>
      </ul>
    </li>
  </ul>
</template>

<script>
import Calculator from './components/Calculator.vue'

export default {
  name: 'App',
  components: {
    Calculator,
  },
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
.cta {
  font-weight: bold;
}
</style>
