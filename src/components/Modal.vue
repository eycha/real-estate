<template>
    <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>{{ rooms[clicked].title}}</h4>
      <p>{{ rooms[clicked].content}}</p>
      <p>{{ rooms[clicked].price}}</p>
      <!-- <button @click="모달창열렸니=flase">X</button> -->
    </div>
  </div>
</template>

<script>
export default {
    //eslint-disable-next-line
    name : 'Modal',
    props : {
        rooms : Object,
        clicked : Number,
        모달창열렸니 : Boolean,
    }
}
</script>

<style>

</style>