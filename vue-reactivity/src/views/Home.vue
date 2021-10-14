<template>
  <div class="home">
    <ProductPage msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import ProductPage from "@/components/en-product-page.vue";

export default {
  name: "Home",
  components: {
    ProductPage,
  },
};
</script>
