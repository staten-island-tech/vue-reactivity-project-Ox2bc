<template>
  <div class="home">
    <div v-if="langRu == true">
      <RuProductPage msg="Welcome to Your Vue.js App" />
    </div>
    <div v-else><EnProductPage msg="Welcome to Your Vue.js App" /></div>
    <div class="footer">
      <main @click="langRu = true">
        <button class="language-button">
          Change Language to {{ langOne }}
        </button>
      </main>
      <main @click="langRu = false">
        <button class="language-button">
          Change Language to {{ langTwo }}
        </button>
      </main>
    </div>
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
      langOne: "Russian",
      langTwo: "English",
    };
  },
};
</script>

<style scoped lang="scss">
.footer {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  color: white;
  text-align: center;
  background-color: #42b983;
  opacity: 80%;
  height: 7.5vh;
}

.language-button {
  display: flex;
  align-items: center;
  border-radius: 20%;
  height: 6vh;
  opacity: 100%;
  border: none;
  text-align: center;
  width: 7.5vw;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
  font-size: 1rem;
}
</style>
