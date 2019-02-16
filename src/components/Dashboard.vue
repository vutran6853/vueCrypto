<template>
  <div>
    <h3>Price</h3>
    <ul>
      <li>EUR: {{ currentPriceValue.EUR }}</li>
      <li>JPY: {{ currentPriceValue.JPY }}</li>
      <li>USD: {{ currentPriceValue.USD }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Dashboard',
  props: {
    currentPriceValue: {}
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
