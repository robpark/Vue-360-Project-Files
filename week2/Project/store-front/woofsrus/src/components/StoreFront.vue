<template>
  <div>
    <ul v-for="product in products" :key="product">
      <li>{{ product }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "StoreFront",
  data() {
    return {
      product: "",
      products: [
        'product1',
        'product2'
      ]
    };
  }
}
</script>

<style scoped>
li {
  list-style: none;
}
</style>
