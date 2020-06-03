<template>
  <div class="home">
    <img alt="Woof" src="../assets/paw-print.jpg" />
    <StoreFront msg="woof... woof..." />
  </div>
</template>

<script>
import StoreFront from "@/components/StoreFront.vue";

export default {
  name: "Home",
  components: {
    StoreFront
  }
};
</script>
