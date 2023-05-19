<template>
  <div>
    <img :src="room.image" class="room-img">
    <h4 @click="send()">{{ room.title }}</h4>
    <p>{{ room.price }}</p>
  </div>
  
</template>

<script>
export default {
    //eslint-disable-next-line
    name : 'Card',
    props : {
        room:Object,
    },
    methods : {
      send() {
        this.$emit('openModal',this.room.id)
      }
    }

}
</script>

<style>

</style>