<template>
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
export default {
  name: 'CalculationsGuide'
}
</script>
