<template>
  

  

  <!-- <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>{{ rooms[clicked].title}}</h4>
      <p>{{ rooms[clicked].content}}</p>
      <p>{{ rooms[clicked].price}}</p>
      <button @click="모달창열렸니=flase">X</button>
    </div>
  </div> -->


  <Modal @closeModal="모달창열렸니=$event" :rooms="rooms" :clicked="clicked" :모달창열렸니="모달창열렸니"/>

  <div class="menu">
    <a v-for="작명 in 메뉴들" :key="작명">{{ 작명 }}</a>
  </div>
  
  <Discount/>

  <Card @openModal="모달창열렸니=true; clicked=$event"  :room="rooms[i]" v-for="(room,i) in rooms" :key="i"/>
  
  
</template>

<script>
import data from './assets/oneroom.js';
import Discount from './components/Discount.vue';
import Modal from './components/Modal.vue';
import Card from './components/Card.vue';



export default {
  name: 'App',
  data() {
    return {
      오브젝트 : { name : 'kim', age : 20},
      clicked : 0,
      rooms : data,
      모달창열렸니 : false,
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods : {
        
    
  },
  components: {
    Discount : Discount,
    Modal : Modal,
    Card : Card,
    
  }
}
</script>

<style>
body {
  margin: 0
}
div {
  box-sizing : border-box;
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


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color : white;
  padding: 10px;

}

.room-img {
  width: 50%;
  margin-top: 40px;
}


</style>
