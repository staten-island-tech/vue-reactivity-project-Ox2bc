<template>
  <div class="about">
    <Wishlist msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import Wishlist from "@/components/en-wishlist.vue";

export default {
  name: "about",
  components: {
    Wishlist,
  },
};
</script>