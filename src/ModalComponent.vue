<template>
    <div class="black-bg" v-if="모달창열렸니==true">
        <div class="white-bg">
            <div class = "room-img">
                <img :src="원룸들[누른거].image" style="width:400px; height:300px">
                <h4>{{ 원룸들[누른거].title }}</h4>
                <p>{{ 원룸들[누른거].content }}</p>
                <!-- <input @input="month = $event.target.value"> -->
                <input :value = "month" type="text" @input="filter">
                <p>{{ month }}개월 선택함 : {{ 원룸들[누른거].price * month }}</p>
                <button @click="$emit('closeModal')">닫기</button>
            </div>
    </div>
</div>
</template>

<script>
export default {
    name : 'ModalComponent',
    data(){
        return{
            month : 1,
        }
    },

    props : {
        원룸들 : Object,
        누른거 : Number,
        모달창열렸니 : Boolean,
    },
    methods : {
        filter(event) {
      // 숫자만 남기고 업데이트
      if(event.target.value.match(/[^0-9]/g)){
                alert('문자는안됨ㅋㅋ');
                event.target.value=1;
            }
      this.month = event.target.value.replace(/[^0-9]/g, "");
      event.target.value = this.month;
    },
    }
}
</script>

<style>
body{
    margin : 0;
}
div {
    box-sizing : border-box;
}
.black-bg{
    width : 100%; height:100%;
    background :  rgba(0,0,0,0.5);
    position:fixed; padding:20px;
}
.white-bg{
    width:100%; background: white;
    border-radius: 8px;
    padding:20px;
}
</style>