<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">{{ProductPage}}</router-link> |
      <router-link to="/about">{{ Wishlist }}</router-link>

    </div>
    <router-view/>
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
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

.cart-logo{
  height: 3vh;
  width: 3vh;
}
</style>

<script>
export default {
  el: "#app",
  data() {
    return({
      ProductPage: "Product Page",
      Wishlist: "Wishlist"
  });
}}
</script>
