<template>
  <div class="home">
    <!-- <main class="language-button" v-on:click="langRu = true">
      <button>Ru</button>
    </main>
    <main
      class="language-button"
      v-on:click="langRu = false"    >
      <button>En</button>
    </main> -->
    <div v-if="langRu == true">
      <RuProductPage msg="Welcome to Your Vue.js App" />
    </div>
    <div v-else><EnProductPage msg="Welcome to Your Vue.js App" /></div>
  </div>
</template>

<script>
// @ is an alias to /src
import RuProductPage from "@/components/ru-product-page.vue";
import EnProductPage from "@/components/en-product-page.vue";

export default {
  name: "Home",
  components: {
    EnProductPage,
    RuProductPage,
  },
  data() {
    return {
      //langRu: true,
    };
  },
};
</script>
