<template>
  <div class="output">
    <h1>{{ msg }}</h1>
    <h3>Input 1</h3>
    <h3>Essential Links</h3>
    <h3>Ecosystem</h3>
  </div>
</template>

<script>
export default {
  name: 'Output',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
