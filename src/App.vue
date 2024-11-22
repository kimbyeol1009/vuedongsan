<template>
  <Modal :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니" @closeModal="모달창열렸니=false"/>
  
  <div class="menu">
    <a v-for="(a,i) in 메뉴들" :key="i">{{ a }}</a>
  </div>

  <Card @openModal="모달창열렸니=true; 누른거 = $event" :원룸="원룸들[i]" v-for="(a,i) in 원룸들" :key="i"/>
 
  

</template>

<script>
import data from "@/data"
import Modal from "@/ModalComponent.vue"
import Card from "@/CardComponent.vue"
export default {
  name: 'App',
  data(){
    return{
      메뉴들 : ["Home","Products","About"],
      원룸들 : data,
      모달창열렸니 : false,
      누른거 : 0,
    }
  },
  props : {
    data : Object,
  },
  components: {
    Modal,
    Card,
  },
  methods :{
  }
}
</script>

<style>
.room-img{
  text-align: center;
}
.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
  text-align: center;
}
.menu a{
  color : white;
  padding : 10px;
}
</style>
