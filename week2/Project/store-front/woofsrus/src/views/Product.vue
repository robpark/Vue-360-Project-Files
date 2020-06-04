<template>
  <div class="home">
    <h2>Product View</h2>
    <h4>{{$route.params.id}}</h4>
    <ProductDetail />
  </div>
</template>>

<script>
import ProductDetail from "@/components/ProductDetail.vue";

export default {
  name: "Product",
  components: {
    ProductDetail
  }
};
</script>

<style scoped>

</style>
