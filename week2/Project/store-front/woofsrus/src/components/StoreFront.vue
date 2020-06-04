<template>
  <div>
    <div v-for="product in products" :key="product.id">
      {{ product.title }}
      <img :src="require('../assets/' + product.image)" />
      {{ product.price }}
    </div>
  </div>
</template>

<script>
export default {
  name: "StoreFront",
  data() {
    return {
      product: "",
      products: [
        {
          id: 1,
          title: "Bully Slice",
          price: 998,
          image: "bully-slice.jpg",
          availableInventory: 10,
          rating: 1
        },
        {
          id: 2,
          title: "Meaty Bone",
          price: 798,
          image: "meaty-bone.jpg",
          availableInventory: 5,
          rating: 2
        },
        {
          id: 3,
          title: "Water Friendly Dolphin",
          price: 1498,
          image: "water-friendly-dolphin.jpg",
          availableInventory: 3,
          rating: 3
        }
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
