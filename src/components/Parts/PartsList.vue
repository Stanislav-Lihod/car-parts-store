<script setup>

import PartCard from "@/components/Parts/PartCard.vue";
</script>

<template>
  <div>
    <PartCard
        title="Engine"
        :part-number="['qwerasd', 'q123', 'r443r']"
        location="Poland"
        seller="Store"
        car="Volkswagen Multivan T5"
        :delivery="3.99"
        :fee="true"
        image="https://images.ovoko.com/bl/581x436/imp/0/0/1/5/4/9/7/3/2/5a7377c5871abc6ae8d08bedb1228a24-acura_legend_i_kiti_valdymo_blokai_moduliai.jpg"
        :price="750"
        :isFavorite="false"
        :inBasket="false"
    />
    <PartCard location="lithuania" :isFavorite="true" :in-basket="true"/>
    <PartCard :part-number="['123','124']"/>
    <PartCard/>
    <PartCard/>
  </div>
</template>

<style lang="less" scoped>

</style>