<template>
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
</template>

<script>
export default {
  name: 'CalculatorInfo'
}
</script>

<style>
.cta {
  font-weight: bold;
}
</style>
