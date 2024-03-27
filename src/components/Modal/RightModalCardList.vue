<script setup>
import PartSmallCard from "@/components/Parts/PartSmallCard.vue";

defineProps({
  cards: Array
})
</script>

<template>
  <div>
    <PartSmallCard
        v-for="(card, index) in cards"
        :data="card"
        :key="index"/>
  </div>
</template>

<style lang="scss" scoped>

</style>