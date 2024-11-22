<template>
  <div class="start" :class="{end : 모달창열렸니}">
    <Modal :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니" @closeModal="모달창열렸니=false"/>
  </div>
  <div class="menu">
    <a v-for="(a,i) in 메뉴들" :key="i">{{ a }}</a>
  </div>
  <Discount v-if="showDiscount==true" :cnt="cnt" :showDiscount="showDiscount"/>
  
  <Card @openModal="모달창열렸니=true; 누른거 = $event" :원룸="원룸들[i]" v-for="(a,i) in 원룸들" :key="i"/>
  
 
  

</template>

<script>
import data from "@/data"
import Modal from "@/ModalComponent.vue"
import Card from "@/CardComponent.vue"
import Discount from "@/DiscountComponent.vue"
export default {
  name: 'App',
  data(){
    return{
      메뉴들 : ["Home","Products","About"],
      원룸들 : data,
      모달창열렸니 : false,
      누른거 : 0,
      cnt : 20,
      showDiscount : true,
    }
  },
  props : {
    data : Object,
  },
  mounted(){
    setInterval(()=>{
      this.cnt -= 1;
      if(this.cnt==0){
        this.showDiscount=false;
      }
    },1000)
  },
  components: {
    Modal,
    Card,
    Discount,
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
.start{
    opacity: 0;
    transition : all 1s;
}
.end{
    opacity: 1;
}
</style>
