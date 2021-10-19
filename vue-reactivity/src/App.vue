<template>
  <div id="app">
    <section id="nav">
      <main class="nav-bar">
        <router-link to="/">{{ ProductPage }}</router-link>
        <router-link to="/about">{{ Wishlist }}</router-link>
      </main>
    </section>
    <router-view />
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding-top: 7.5vh;
  padding-bottom: 12.5vh;
  font-size: 1.25rem;
  display: flex;
  justify-content: center;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

.nav-bar {
  width: 25vw;
  display: flex;
  justify-content: space-evenly;
}

.language-button {
  width: 10vw;
  display: flex;
  justify-content: flex-end;
}
</style>

<script>
export default {
  el: "#app",
  props: ["langRu"],
  data() {
    return {
      ProductPage: "Product Page",
      Wishlist: "Wishlist",
    };
  },
};
</script>
