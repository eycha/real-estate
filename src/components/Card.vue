<template>
    <div v-for="(room,i) in rooms" :key="i">
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
        rooms:Object,

        
    }

}
</script>

<style>

</style>