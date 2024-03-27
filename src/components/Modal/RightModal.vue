<script setup>
import ActionButton from "@/components/Feature/ActionButton.vue";
import RightModalEmptyContent from "@/components/Modal/RightModalEmptyContent.vue";
import {ref} from "vue";
import RightModalCardList from "@/components/Modal/RightModalCardList.vue";

const cards = ref([{
  title:"Engine",
  partNumber:"['qwerasd', 'q123', 'r443r']",
  location:"Poland",
  seller:"Store",
  car:"Volkswagen Multivan T5",
  delivery:"3.99",
  fee:"true",
  image:"https://images.ovoko.com/bl/581x436/imp/0/0/1/5/4/9/7/3/2/5a7377c5871abc6ae8d08bedb1228a24-acura_legend_i_kiti_valdymo_blokai_moduliai.jpg",
  price:"750",
},{
  title:"Roof airbag",
  partNumber:"['qwerasd', 'q123', 'r443r']",
  location:"Poland",
  seller:"Store",
  car:"Volkswagen Multivan T5",
  delivery:"3.99",
  fee:"true",
  image:"https://images.ovoko.com/bl/581x436/imp/0/0/1/5/4/9/7/3/2/5a7377c5871abc6ae8d08bedb1228a24-acura_legend_i_kiti_valdymo_blokai_moduliai.jpg",
  price:"750",
},{
  title:"Sliding door lock",
  partNumber:"['qwerasd', 'q123', 'r443r']",
  location:"Lithuania",
  seller:"Store",
  car:"Volkswagen Multivan T5",
  delivery:"3.99",
  fee:"true",
  image:"https://images.ovoko.com/bl/581x436/imp/0/0/1/5/4/9/7/3/2/5a7377c5871abc6ae8d08bedb1228a24-acura_legend_i_kiti_valdymo_blokai_moduliai.jpg",
  price:"750",
}])

const openModal = () =>{
  document.body.style.overflow = 'hidden'
}
openModal()
</script>

<template>
  <div class="modal">
    <div class="modal__content">
      <ActionButton type="close" :is-active="false" :on-click-change-status="()=>{}" class="modal__close-btn"/>
      <RightModalEmptyContent v-if="cards.length === 0" type="basket" title="Your basket is empty"/>
      <RightModalCardList v-else :cards="cards"/>
    </div>
  </div>
</template>

<style lang="less" scoped>
.modal{
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0,0,0, 0.6);
  display: flex;
  justify-content: flex-end;

  &__content{
    padding: 24px;
    min-width: 350px;
    max-width: 600px;
    width: 30%;
    height: 100%;
    background-color: white;
    display: flex;
    flex-direction: column;
    gap: 24px 8px;
  }

  &__close-btn{
    align-self: flex-end;
  }
}
</style>