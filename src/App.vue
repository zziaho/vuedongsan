<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <h4 :style="style">XX 원룸</h4>
    <p>{{ price1 }} 만원</p>
  </div>
  <div>
    <h4>XX 원룸</h4>
    <p>{{ price2 }} 만원</p>
  </div>
  
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      price1 : 30,
      price2 : 50,
      style : 'color : blue'
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
</style>
