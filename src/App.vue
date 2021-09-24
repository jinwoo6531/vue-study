<template>

  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="modal = false">닫기</button>
    </div>
  </div>
<div class="menu">
  <a v-for="(item,i) in menus" :key="i">{{item}}</a>
</div>  
  <div  v-for="(item,i) in oneroom" :key="i">
    <img :src="item.image" class="room-img">
    <h4 @click="modal = true">{{item.title}}</h4>
    <p>{{item.price}} 만원</p>
    
    <br/><br/>
  </div>

</template>

<script>

import data from './post';

export default {
  name: 'App',
  data() {
    return {
      oneroom: data,
      modal: false,
      num: [0,0,0],
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

body{
  margin:0
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width:100%;
  background: white;
  border-radius: 8px;
  padding:20px;
}




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
