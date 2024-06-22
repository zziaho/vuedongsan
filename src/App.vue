<template>

  <div class="black-bg" v-if="isModalOpen">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="closeModal">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(menu, index) in menus" :key="index">{{ menu }}</a>
  </div>


  <div v-for="(product, index) in products" :key="index">
    <img :src="(require(`./assets/room${index}.jpg`))" class="room-img">
    <h4 @click="openModal">{{ product.name }}</h4>
    <p>{{ product.price }}</p>
    <button @click="increseReportCnt(index)">허위매물신고</button>
    <span>신고수 : {{ product.reportCnt }}</span>
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
          imgUrl: './assets/room',
          ext: '.jpg',
        },
        {
          name: '천호동원룸',
          price: '50만원',
          reportCnt: 0,
          imgUrl: './assets/room',
          ext: '.jpg',
        },
        {
          name: '마포구원룸',
          price: '70만원',
          reportCnt: 0,
          imgUrl: './assets/room',
          ext: '.jpg',
        },
      ],
      menus: ['Home', 'Shop', 'About'],
      isModalOpen: false,
    }
  },
  methods: {
    increseReportCnt(index) {
      this.products[index].reportCnt += 1;
    },
    openModal() {
      this.isModalOpen = true;
    },
    closeModal() {
      this.isModalOpen = false;
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

.room-img {
  width: 60%;
  margin-top: 40px;
}

.menu a {
  color: white;
  padding: 10px;
}

body {
  margin : 0
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
