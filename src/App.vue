<template>
  

  

  <!-- <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>{{ rooms[clicked].title}}</h4>
      <p>{{ rooms[clicked].content}}</p>
      <p>{{ rooms[clicked].price}}</p>
      <button @click="모달창열렸니=flase">X</button>
    </div>
  </div> -->

  <transition name="fade">
    <Modal @closeModal="모달창열렸니=$event" :rooms="rooms" :clicked="clicked" :모달창열렸니="모달창열렸니"/>
  </transition>


  <div class="menu">
    <a v-for="작명 in 메뉴들" :key="작명">{{ 작명 }}</a>
  </div>
  
  <Discount v-if="showDiscount == true" :discountPercent="discountPercent"/>

  <button @click="priceSort">가격순정렬</button>
  <button @click="sortBack">되돌리기</button>

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
      showDiscount : true,
      discountPercent : 20,
      오브젝트 : { name : 'kim', age : 20},
      clicked : 0,
      roomsOrigin : [...data],
      rooms : data,
      모달창열렸니 : false,
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods : {
    priceSort() {
      this.rooms.sort(function(a,b) {
        return a.price -b.price;
      });
    },
    sortBack() {
      this.rooms = [...this.roomsOrigin];
    }
    
  },
  components: {
    Discount : Discount,
    Modal : Modal,
    Card : Card,
    
  },
  mounted() {

    if(this.discountPercent > 0) {
      setInterval(()=> {
        this.discountPercent = this.discountPercent-1;
        
      }, 1000)

    

    

    
  }
},
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

.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 1s;
}
.fade-enter-to {
  opacity: 1;
}

</style>
