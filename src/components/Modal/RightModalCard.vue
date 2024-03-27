<script setup>
defineProps({
  title: String
})
</script>

<template>
  <div class="card">{{title}}</div>
</template>

<style lang="less" scoped>
.card{
  border-radius: 4px;
  border: 1px solid #e7e7e7;
  transition: .3s;
  padding: 8px;

  &:hover{
    background-color: rgba(0, 0, 0, .04);
  }

  &:not(:last-child){
    margin-bottom: 16px;
  }
}
</style>