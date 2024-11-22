<template>
   <div>
    <img :src="원룸.image" class="room-img" style="width:100%">
    <h4 @click="$emit('openModal',원룸.id)">{{ 원룸.title }}</h4>
    <p>{{원룸.price }}</p>
  </div>
</template>

<script>
export default {
    name : "CardComponent",
    data(){
        return{

        }
    },
    props : {
        원룸 : Object,
    },
}
</script>

<style>

</style>