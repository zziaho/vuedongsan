<template>

  <div class="menu">
    <a v-for="(menu, index) in menus" :key="index">{{ menu }}</a>
  </div>

  <img alt="Vue logo" src="./assets/logo.png">

  <div v-for="(product, index) in products" :key="index">
    <h4>{{ product.name }}</h4>
    <p>{{ product.price }}</p>
  </div>
  
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      price1: 30,
      price2: 50,
      blueFont: 'color : blue',
      products: [
        {
          name: '역삼동원룸',
          price: '30만원'
        },
        {
          name: '천호동원룸',
          price: '50만원'
        },
        {
          name: '마포구원룸',
          price: '70만원'
        },
      ],
      menus: ['Home', 'Shop', 'About'],
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
