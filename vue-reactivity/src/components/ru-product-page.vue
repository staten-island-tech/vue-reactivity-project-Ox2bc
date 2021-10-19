<template>
  <section class="main-sect">
    <section class="product-page">
      <div class="airpods-div">
        <img
          v-if="(airpodsOpacity = false)"
          :style="{ opacity: fullOpacity }"
          class="airpods-image"
          src="../assets/airpods-1.png"
          alt=""
        />
        <img
          v-else
          v-bind:style="{ opacity: halfOpacity }"
          class="airpods-image"
          src="../assets/airpods-1.png"
          alt=""
        />
        <main v-if="airpodsStock > 5" class="airpods-stock">
          На исходе! Осталось всего {{ airpodsStock }}
        </main>
        <main
          v-else-if="airpodsStock <= 5 && airpodsStock > 0"
          class="airpods-stock"
        >
          Торопиться! Tолько {{ airpodsStock }} oсталось!
        </main>
        <p v-else class="airpods-stock">
          Извините, Airpods полностью распродан
        </p>
        <button
          v-if="airpodsStock > 0"
          v-on:click="airpodsStock -= 1"
          class="airpods-button"
        >
          <p>Купить сейчас</p>
        </button>
        <button
          v-else
          v-on:click="airpodsStock -= 1"
          disabled="true"
          class="airpods-button-disabled"
        >
          <p>Извините</p>
        </button>
      </div>
      <div class="macbook-div">
        <img
          v-if="(macbookOpacity = false)"
          :style="{ opacity: fullOpacity }"
          class="macbook-image"
          src="../assets/macbook-1.png"
          alt=""
        />
        <img
          v-else
          v-bind:style="{ opacity: halfOpacity }"
          class="macbook-image"
          src="../assets/macbook-1.png"
          alt=""
        />
        <main v-if="macbookStock > 5" class="macbook-stock">
          На исходе! Осталось всего {{ macbookStock }}
        </main>
        <main
          v-else-if="macbookStock <= 5 && macbookStock > 0"
          class="macbook-stock"
        >
          Торопиться! Tолько {{ macbookStock }} oсталось!
        </main>
        <p class="macbook-stock" v-else>
          Извините, Macbook полностью распродан
        </p>
        <button
          v-if="macbookStock > 0"
          v-on:click="macbookStock -= 1"
          class="macbook-button"
        >
          <p>Купить сейчас</p>
        </button>
        <button
          v-else
          v-on:click="macbookStock -= 1"
          disabled="true"
          class="macbook-button-disabled"
        >
          Извините
        </button>
      </div>
      <div class="iphone-div">
        <img
          v-if="(iphoneOpacity = false)"
          :style="{ opacity: fullOpacity }"
          class="iphone-image"
          src="../assets/iphone-1.png"
          alt=""
        />
        <img
          v-else
          v-bind:style="{ opacity: halfOpacity }"
          class="iphone-image"
          src="../assets/iphone-1.png"
          alt=""
        />
        <main v-if="iphoneStock > 5" class="iphone-stock">
          На исходе! Осталось всего {{ iphoneStock }}
        </main>
        <main v-else-if="iphoneStock <= 5 && iphoneStock > 0">
          Торопиться! Tолько {{ iphoneStock }} oсталось!
        </main>
        <p v-else class="iphone-stock">Извините, iPhone полностью распродан</p>
        <button
          v-if="iphoneStock > 0"
          v-on:click="iphoneStock -= 1"
          class="iphone-button"
        >
          <p>Купить сейчас</p>
        </button>
        <button
          v-else
          v-on:click="iphoneStock -= 1"
          disabled="true"
          class="iphone-button-disabled"
        >
          Извините
        </button>
      </div>
      <div class="surface-div">
        <img
          v-if="(surfaceOpacity = false)"
          :style="{ opacity: fullOpacity }"
          class="surface-image"
          src="../assets/surface-1.png"
          alt=""
        />
        <img
          v-else
          v-bind:style="{ opacity: halfOpacity }"
          class="surface-image"
          src="../assets/surface-1.png"
          alt=""
        />
        <main v-if="surfaceStock > 5" class="surface-stock">
          На исходе! Осталось всего {{ surfaceStock }}
        </main>
        <main v-else-if="surfaceStock <= 5 && surfaceStock > 0">
          Торопиться! Tолько {{ surfaceStock }} oсталось!
        </main>
        <p v-else class="surface-stock">
          Извините, Surface полностью распродан
        </p>
        <button
          v-if="surfaceStock > 0"
          v-on:click="surfaceStock -= 1"
          class="surface-button"
        >
          Купить сейчас
        </button>
        <button
          v-else
          v-on:click="surfaceStock -= 1"
          disabled="true"
          class="surface-button-disabled"
        >
          Извините
        </button>
      </div>
    </section>
  </section>
</template>

<script>
export default {
  name: "productPage",
  props: {
    msg: String,
  },
  data() {
    return {
      airpodsStock: 2,
      macbookStock: 9,
      iphoneStock: 4,
      surfaceStock: 7,
      airpodsOpacity: false,
      macbookOpacity: false,
      iphoneOpacity: false,
      surfaceOpacity: false,
      halfOpacity: "50%",
      fullOpacity: "100",
    };
  },
  methods: {
    opacityAirpods() {
      if (this.airpodsStock > 0) {
        this.airpodsOpacity = false;
      } else {
        this.airpodsOpacity = true;
      }
    },
    opacityMacbook() {
      if (this.macbookStock > 0) {
        this.macbookOpacity = false;
      } else {
        this.macbookOpacity = true;
      }
    },
    opacityIphone() {
      if (this.iphoneStock > 0) {
        this.iphoneOpacity = false;
      } else {
        this.iphoneOpacity = true;
      }
    },
    opacitySurface() {
      if (this.surfaceStock > 0) {
        this.surfaceOpacity = false;
      } else {
        this.surfaceOpacity = true;
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.product-page {
  display: flex;
  justify-content: space-evenly;
}

.airpods-div {
  border: 15px solid white;
  border-bottom: 10vh solid white;
  outline: 1px solid #42b983;
}

.airpods-image {
  height: 20vh;
}

.macbook-div {
  border: 15px solid white;
  border-bottom: 10vh solid white;
  outline: 1px solid #42b983;
}

.macbook-image {
  height: 20vh;
}

.iphone-div {
  border: 15px solid white;
  border-bottom: 10vh solid white;
  outline: 1px solid #42b983;
}

.iphone-image {
  height: 20vh;
}

.surface-div {
  border: 15px solid white;
  border-bottom: 10vh solid white;
  outline: 1px solid #42b983;
}

.surface-image {
  height: 20vh;
}

.stock-amount {
  display: flex;
  justify-content: space-evenly;
}

.purchase-buttons {
  display: flex;
  justify-content: space-evenly;
}

.airpods-button {
  height: 8.5vh;
  width: 8.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.macbook-button {
  height: 8.5vh;
  width: 8.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.iphone-button {
  height: 8.5vh;
  width: 8.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.surface-button {
  height: 8.5vh;
  width: 8.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: bolder;
}

.airpods-button-disabled {
  height: 7.5vh;
  width: 7.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.macbook-button-disabled {
  height: 7.5vh;
  width: 7.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.iphone-button-disabled {
  height: 7.5vh;
  width: 7.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.surface-button-disabled {
  height: 7.5vh;
  width: 7.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}
</style>