<template>
  <section class="wishlist">
    <p class="wish-title">Wishlist</p>
    <input
      class="wish-input"
      v-model="newItem"
      v-on:keyup.enter="addTask"
      placeholder="Wishlist"
    />
    <ul class="wishlist-ul">
      <li class="wishlist-li" v-for="item in items" :key="item">
        ❖ {{ item }}
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: "Wishlist",
  props: {
    msg: String,
  },
  data() {
    return {
      items: [],
      newItem: "",
    };
  },
  methods: {
    addTask() {
      if (this.newItem.length > 0) {
        this.items.push(this.newItem);
        this.newItem = "";
      }
    },
  },
};
</script>

<style scoped lang="scss">
.wishlist {
  height: 85vh;
}

.wish-title {
  height: 5vh;
  font-size: 5vh;
  font-weight: bold;
  margin: 3vh;
}

.wishlist-ul {
  list-style: none;
}

.wish-input {
  width: 50%;
  padding: 10px;
  margin: 1vh;
  border: none;
  border-bottom: 2px solid #42b983;
}

.wishlist-li {
  font-size: 2.5vh;
}
</style>