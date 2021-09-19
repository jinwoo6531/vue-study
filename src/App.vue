<template>
<div class="menu">
  <a v-for="(item,i) in menus" :key="i">{{item}}</a>
</div>

  <img alt="Vue logo" src="./assets/logo.png">

  <div v-for="(item,i) in products" :key="i">
    {{item}}
    <button @click="increase">허위매물신고</button> <span>신고수 : {{num}}</span>
  </div>

  
  
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      num: 0,
      menus: ['Home', 'Products', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸']
    }
  },
  methods: {
    increase(){
      this.num += 1;
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

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
