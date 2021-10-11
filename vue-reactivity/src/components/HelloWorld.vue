<template>
  <div class="hello">
    <js msg="Welcome to Your Vue.js App"/>
    <div class="product-page">
      <div class="airpods">
        <img v-if="airpodsOpacity = false" :style="{opacity: fullOpacity}" class="airpods-image" src="../assets/airpods-1.png" alt="">
        <img v-else v-bind:style="{opacity: halfOpacity}" class="airpods-image" src="../assets/airpods-1.png" alt="">
      </div>
      <div class="macbook">
        <img v-if="macbookOpacity = false" :style="{opacity: fullOpacity}" class="macbook-image" src="../assets/macbook-1.png" alt="">
        <img v-else v-bind:style="{opacity: halfOpacity}" class="macbook-image" src="../assets/macbook-1.png" alt="">
      </div>
      <div class="iphone">
        <img v-if="iphoneOpacity = false" :style="{opacity: fullOpacity}" class="iphone-image" src="../assets/iphone-1.png" alt="">
        <img v-else v-bind:style="{opacity: halfOpacity}" class="iphone-image" src="../assets/iphone-1.png" alt="">
      </div>
      <div class="surface">
        <img v-if="surfaceOpacity = false" :style="{opacity: fullOpacity}" class="surface-image" src="../assets/surface-1.png" alt="">
        <img v-else v-bind:style="{opacity: halfOpacity}" class="surface-image" src="../assets/surface-1.png" alt="">
      </div>
    </div>
    <div class="stock-amount">
      <!-- Airpods -->
      <div v-if="airpodsStock > 5" class="airpods-stock">
        Running Low! Only {{ airpodsStock }} left!
      </div>
      <div v-else-if="airpodsStock <= 5 && airpodsStock >0">
        Hurry Up! Only {{ airpodsStock }} left!
      </div>
      <div v-else>
        Sorry, Airpods are Sold Out
      </div>
      <!-- Macbook -->
      <div v-if="macbookStock > 5" class="macbook-stock">
        Running Low! Only {{ macbookStock }} left!
      </div>
      <div v-else-if="macbookStock <= 5 && macbookStock >0">
        Hurry Up! Only {{ macbookStock }} left!
      </div>
      <div v-else>
        Sorry, Macbook is Sold Out
      </div>
      <!-- iPhone -->
      <div v-if="iphoneStock > 5" class="iphone-stock">
        Running Low! Only {{ iphoneStock }} left!
      </div>
      <div v-else-if="iphoneStock <= 5 && iphoneStock >0">
        Hurry Up! Only {{ iphoneStock }} left!
      </div>
      <div v-else>
        Sorry, iPhone is Sold Out
      </div>
      <!-- Surface -->
      <div v-if="surfaceStock > 5" class="surface-stock">
        Running Low! Only {{ surfaceStock }} left!
      </div>
      <div v-else-if="surfaceStock <= 5 && surfaceStock >0">
        Hurry Up! Only {{ surfaceStock }} left!
      </div>
      <div v-else>
        Sorry, Surface is Sold Out
      </div>
    </div>
    <div class="purchase-buttons">
      <button v-if="airpodsStock > 0" v-on:click="airpodsStock -= 1" class="airpods-button">
        Buy Now
      </button>
      <button v-else v-on:click="airpodsStock -= 1" disabled="true" class="airpods-button-disabled">
        Sorry
      </button>
      <button v-if="macbookStock > 0" v-on:click="macbookStock -= 1" class="macbook-button">
        Buy Now
      </button>
      <button v-else v-on:click="macbookStock -= 1" disabled="true" class="macbook-button-disabled">
        Sorry
      </button>
      <button v-if="iphoneStock > 0" v-on:click="iphoneStock -= 1" class="iphone-button">
        Buy Now
      </button>
      <button v-else v-on:click="iphoneStock -= 1" disabled="true" class="iphone-button-disabled">
        Sorry
      </button>
      <button v-if="surfaceStock > 0" v-on:click="surfaceStock -= 1" class="surface-button">
        Buy Now
      </button>
      <button v-else v-on:click="surfaceStock -= 1" disabled="true" class="surface-button-disabled">
        Sorry
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return({
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
    })
  },
  methods:{
    opacityAirpods(){
      if(this.airpodsStock > 0){
        this.airpodsOpacity = false;
      }
      else{
        this.airpodsOpacity = true;
      }
    },
    opacityMacbook(){
      if(this.macbookStock > 0){
        this.macbookOpacity = false;
      }
      else{
        this.macbookOpacity = true;
      }
    },
    opacityIphone(){
      if(this.iphoneStock > 0){
        this.iphoneOpacity = false;
      }
      else{
        this.iphoneOpacity = true;
      }
    },
    opacitySurface(){
      if(this.surfaceStock > 0){
        this.surfaceOpacity = false;
      }
      else{
        this.surfaceOpacity = true;
      }
    }
  }
}
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

.product-page{
  display: flex;
  justify-content: space-evenly;
}

.airpods{
  display: flex;
  align-items: center;
  justify-content: center;
  height: 30vh;
  width: 80px;
}

.airpods-image{
  height: 20vh;
}

.macbook{
  display: flex;
  align-items: center;
  justify-content: center;
  height: 30vh;
  width: 80px;
}

.macbook-image{
  height: 20vh;
}

.iphone{
  display: flex;
  align-items: center;
  justify-content: center;
  height: 30vh;
  width: 80px;
}

.iphone-image{
  height: 20vh;
}

.surface{
  display: flex;
  align-items: center;
  justify-content: center;
  height: 30vh;
  width: 80px;
}

.surface-image{
  height: 20vh;
}

.stock-amount{
  display: flex;
  justify-content: space-evenly;
}

.purchase-buttons{
  display: flex;
  justify-content: space-evenly;
}

.airpods-button{
  height: 7.5vh;
  width: 7.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.macbook-button{
  height: 7.5vh;
  width: 7.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.iphone-button{
  height: 7.5vh;
  width: 7.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.surface-button{
  height: 7.5vh;
  width: 7.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: bolder;
}

.airpods-button-disabled{
  height: 7.5vh;
  width: 7.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.macbook-button-disabled{
  height: 7.5vh;
  width: 7.5vw;
  border-radius: 28px;
  color: white;
  background: #3c94c3;
  font-weight: 700;
}

.iphone-button-disabled{
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


