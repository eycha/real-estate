<template>
  <div>
    <img :src="room.image" class="room-img">
    <h4>{{ room.title }}</h4>
    <p>{{ room.price }}</p>
  </div>
  
</template>

<script>
export default {
    //eslint-disable-next-line
    name : 'Card',
    props : {
        room:Object,

        
    }

}
</script>

<style>

</style>