<template>
    <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>{{ rooms[clicked].title}}</h4>
      <p>{{ rooms[clicked].content}}</p>
      <input v-model="month">
      <p>{{month}}개월 선택함 : {{rooms[clicked].price * month}}원</p>
      <button @click="close()">X</button>
    </div>
  </div>
</template>

<script>
export default {
    //eslint-disable-next-line
    name : 'Modal',
    data() {
      return {
        month :1,

      }
    },
    props : {
      rooms : Object,
      clicked : Number,
      모달창열렸니 : Boolean,
    },
    methods : {
      
      close() {
        this.$emit('closeModal',false)
      }

    }
}
</script>

<style>

</style>