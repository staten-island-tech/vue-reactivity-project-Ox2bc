<template>
  <div class="home">
    <div v-if="langRu == true">
      <RuProductPage msg="Welcome to Your Vue.js App" />
    </div>
    <div v-else><EnProductPage msg="Welcome to Your Vue.js App" /></div>
    <main class="language-button" @click="langRu = true">
      <button @click="changeLang">Change Language to {{ currentLang }}</button>
    </main>
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
      currentLang: "Russian",
      langRu: false,
      langRuTwo: false,
    };
  },
  methods: {
    changeLang() {
      if (this.langRu == false) {
        this.langRuTwo = true;
      } else {
        this.langRuTwo = false;
      }
      if (this.langRuTwo == true) {
        this.currentLang = "English";
      } else {
        this.currentLang = "Russian";
      }
    },
  },
};
</script>
