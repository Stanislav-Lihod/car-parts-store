<script setup>
  defineProps({
    type: String,
    title: String
  })
</script>

<template>
  <div class="content">
    <img :src="`src/assets/icons/${type}.svg`" :alt="type">
    {{ title }}
  </div>
</template>

<style lang="less" scoped>
.content{
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 24px;

  img{
    width: 40%;
  }
}
</style>