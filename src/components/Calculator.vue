<template>
  <div class="calculator">
    <h1>{{ msg }}</h1>
    <div class="input">
      <h3>Are you calculating for a clothing item or an accessory? *</h3>
      <select name="item-type" id="item-type-select" v-model="itemType">
        <option value="clothing">Clothing Item</option>
        <option value="accessory">Accessory</option>
      </select>
    </div>
    <div class="input">
      <h3>Recommended Retail Price (RRP) *</h3>
      <input type="number" id="item-rrp-select" v-model="rrp" />
      <!--TODO: add euro symbol to left-hand side-->
      <p>How much does your item cost if bought new?</p>
    </div>
    <div class="input">
      <h3>{{ cleaningOrRepairLabel }}</h3>
      <h3>€{{ cleaningOrRepairCost }}</h3>
      <input
        type="range"
        id="item-cleaning-cost-select"
        min="0"
        max="50"
        step="1"
        v-model="cleaningOrRepairCost"
      />
      <p>
        How much will it cost to {{ cleaningOrRepairVerb }} the item after each
        booking?
      </p>
    </div>
    <div class="input">
      <h3>Minimum Rental Period *</h3>
      <select
        name="item-rental-period"
        id="item-rental-period-select"
        v-model="rentalPeriodInDays"
      >
        <option value="7">One Week (7 Days)</option>
        <option value="14">Two Weeks (14 Days)</option>
        <option value="21">Three Weeks (21 Days)</option>
        <option value="30">One Month (30 Days)</option>
      </select>
      <!--TODO: add euro symbol to left-hand side-->
      <p>
        Indicate the minimum rental period for your item. More extended periods
        have a lower daily price. However, since it has a more extended period,
        the booking value is higher. You make more per booking, and you'll earn
        the item's RRP sooner.
      </p>
    </div>
    <div class="output">
      <h3>Your Recommended Rental Price is</h3>
      <h3>€{{ calculatedRrpPerDay }} per day</h3>
      <p>Sharedrobes' minimum rental price is €1.50 per day.</p>
    </div>
    <div class="output">
      <h3>Which translates into you earning</h3>
      <h3>€{{ calculatedBookingEarning }} per booking</h3>
    </div>
    <div class="output">
      <h3>You will have earned your item's RRP in</h3>
      <h3>{{ calculatedNumberOfBookingsToEarnRrp }} bookings</h3>
      <p>Sharedrobes' minimum rental price is €1.50 per day.</p>
    </div>
  </div>
</template>

<script>
// TODO: set minimum calculatedRrpPerDay to 1 euro 50
const rrpPercentage = {
  7: 0.02,
  14: 0.0175,
  21: 0.015,
  30: 0.0125,
}
export default {
  name: 'Calculator',
  props: {
    msg: String,
  },
  data() {
    return {
      itemType: 'clothing',
      rrp: 50,
      cleaningOrRepairCost: 4,
      rentalPeriodInDays: 7,
    }
  },
  computed: {
    cleaningOrRepairLabel() {
      return this.itemType === 'accessory' ? 'Repair Cost' : 'Cleaning Cost'
    },
    cleaningOrRepairVerb() {
      return this.itemType === 'accessory' ? 'repair' : 'clean'
    },
    calculatedRrpPerDay() {
      return (
        this.rrp * rrpPercentage[this.rentalPeriodInDays] +
        this.cleaningOrRepairCost / this.rentalPeriodInDays
      ).toFixed(2)
    },
    calculatedBookingEarning() {
      return (this.calculatedRrpPerDay * this.rentalPeriodInDays).toFixed(2)
    },
    calculatedNumberOfBookingsToEarnRrp() {
      return (this.rrp / this.calculatedBookingEarning).toFixed(2)
    },
  },
}
</script>

<style scoped>
.input,
.output {
  background-color: #f1f1f1;
  padding: 20px;
  margin: 10px 20px;
  color: black;
}
.output {
  color: #5dbdbf;
}
.input > p,
.output > p {
  font-style: italic;
}
h3 {
  font-weight: 600;
  font-size: 1.5rem;
}
input,
select {
  width: 100%;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
