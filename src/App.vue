<template>

  <div class="menu">
    <a v-for="(menu, index) in menus" :key="index">{{ menu }}</a>
  </div>

  <img alt="Vue logo" src="./assets/logo.png">

  <div v-for="(product, index) in products" :key="index">
    <h4>{{ product.name }}</h4>
    <p>{{ product.price }}</p>
    <button @:click="increseReportCnt(index)">허위매물신고</button> <span>신고수 : {{ product.reportCnt }}</span>
  </div>
  
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      products: [
        {
          name: '역삼동원룸',
          price: '30만원',
          reportCnt: 0,
        },
        {
          name: '천호동원룸',
          price: '50만원',
          reportCnt: 0,
        },
        {
          name: '마포구원룸',
          price: '70만원',
          reportCnt: 0,
        },
      ],
      menus: ['Home', 'Shop', 'About'],
      reportCnt: 0,
    }
  },
  methods: {
    increseReportCnt(index) {
      this.products[index].reportCnt += 1;
    },
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
