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
          <p>Купить сейчаc</p>
        </button>
        <button
          v-else
          v-on:click="airpodsStock -= 1"
          disabled="true"
          class="airpods-button-disabled"
        >
          <p>Извинитe</p>
        </button>
        <main class="airpods-price">
          <main v-if="airpodsSale == false">
            <p class="price">$159</p>
          </main>
          <main v-else>
            <p class="sale-sign">РАСПРОДАЖА</p>
            <p class="sale-normal-price">$159</p>
            <p class="price">$139</p>
          </main>
        </main>
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
          Купить сейчаc
        </button>
        <button
          v-else
          v-on:click="macbookStock -= 1"
          disabled="true"
          class="macbook-button-disabled"
        >
          Извините
        </button>
        <main class="macbook-price">
          <main v-if="macbookSale == false">
            <p class="price">$1,599</p>
          </main>
          <main v-else>
            <p class="sale-sign">РАСПРОДАЖА</p>
            <p class="sale-normal-price">$1,599</p>
            <p class="price">$1,399</p>
          </main>
        </main>
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
        <p v-else>Извините, iPhone полностью распродан</p>
        <button
          v-if="iphoneStock > 0"
          v-on:click="iphoneStock -= 1"
          class="iphone-button"
        >
          Купить сейчас
        </button>
        <button
          v-else
          v-on:click="iphoneStock -= 1"
          disabled="true"
          class="iphone-button-disabled"
        >
          Извините
        </button>
        <main class="iphone-price">
          <main v-if="iphoneSale == false">
            <p class="price">$849</p>
          </main>
          <main v-else>
            <p class="sale-sign">РАСПРОДАЖА</p>
            <p class="sale-normal-price">$849</p>
            <p class="price">$699</p>
          </main>
        </main>
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
        <p v-else>Извините, Surface полностью распродан</p>
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
        <main class="surface-price">
          <main v-if="surfaceSale == false">
            <p class="price">$1,100</p>
          </main>
          <main v-else>
            <p class="sale-sign">РАСПРОДАЖА</p>
            <p class="sale-normal-price">$1,100</p>
            <p class="price">$715</p>
          </main>
        </main>
      </div>
    </section>
    <section>
      <button class="sale-button" v-on:click="rndNumb"></button>
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
      airpodsSale: false,
      macbookSale: false,
      iphoneSale: false,
      surfaceSale: false,
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
    rndNumb() {
      var d = new Date();
      var day = d.getDay();
      console.log(day);
      if (day <= 1) {
        var randairpods = Math.floor(Math.random() * 100);
      } else {
        randairpods = Math.floor(Math.random() * 200);
      }
      if (randairpods < 10) {
        this.airpodsSale = true;
      } else {
        this.airpodsSale = false;
      }
      console.log(this.airpodsSale);
      if (2 <= day <= 3) {
        var randmacbook = Math.floor(Math.random() * 100);
      } else {
        randmacbook = Math.floor(Math.random() * 200);
      }
      if (randmacbook < 10) {
        this.macbookSale = true;
      } else {
        this.macbookSale = false;
      }
      console.log(this.macbookSale);
      if (3 <= day <= 4) {
        var randiphone = Math.floor(Math.random() * 100);
      } else {
        randiphone = Math.floor(Math.random() * 200);
      }
      if (randiphone < 10) {
        this.iphoneSale = true;
      } else {
        this.iphoneSale = false;
      }
      console.log(this.iphoneSale);
      if (5 <= day <= 6) {
        var randsurface = Math.floor(Math.random() * 100);
      } else {
        randsurface = Math.floor(Math.random() * 200);
      }
      if (randsurface < 10) {
        this.surfaceSale = true;
      } else {
        this.surfaceSale = false;
      }
      console.log(this.surfaceSale);
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
  max-height: 32.5vh;
  border: 15px solid white;
  border-bottom: 10vh solid white;
  outline: 1px solid #42b983;
}

.airpods-image {
  height: 20vh;
}

.macbook-div {
  max-height: 32.5vh;
  border: 15px solid white;
  border-bottom: 10vh solid white;
  outline: 1px solid #42b983;
}

.macbook-image {
  height: 20vh;
}

.iphone-div {
  max-height: 32.5vh;
  border: 15px solid white;
  border-bottom: 10vh solid white;
  outline: 1px solid #42b983;
}

.iphone-image {
  height: 20vh;
}

.surface-div {
  max-height: 32.5vh;
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
  height: 7.5vh;
  width: 7.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.macbook-button {
  height: 7.5vh;
  width: 7.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.iphone-button {
  height: 7.5vh;
  width: 7.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.surface-button {
  height: 7.5vh;
  width: 7.5vw;
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

.sale-sign {
  color: red;
  font-weight: 900;
  padding: 0%;
  margin: 5px auto;
}

.sale-normal-price {
  text-decoration: line-through;
  color: red;
  margin: 2.5px auto;
  font-weight: 550;
}

.price {
  margin: 5px auto;
  font-weight: 550;
}

.sale-button {
  border: 2px solid #42b983;
  height: 80px;
  width: 295px;
  border-radius: 4px;
  position: relative;
  cursor: pointer;
  font-family: "Roboto", sans-serif;
  margin: 25px;
  font-size: 0.85rem;
  font-weight: 700;

  &::after {
    content: "Нажмите, чтобы увидеть случайную распродажу! СКИДКА до 35%";
    position: absolute;
    top: 10%;
    left: 50%;
    transform: translate(-50%);
    color: #42b983;
    transition: all 0.1s linear;
  }

  &:hover {
    &::before {
      opacity: 1;
      animation: star 1.3s linear infinite;
    }

    &::after {
      content: "Нажмите, чтобы увидеть случайную распродажу! СКИДКА до 35%";
      color: #42b3;
      filter: saturate(500%);
    }
  }
}
</style>


