<script setup>
defineProps({
  type: String,
  placeholder: String
})
</script>

<template>
  <input :type="type" :placeholder="placeholder">
</template>

<style lang="less" scoped>
input{
  padding: 12px 20px;
  border-radius: 4px;
  border: 1px solid rgba(0,0,0,0.3);
  outline: none;
  transition: .3s;

  &:focus{
    box-shadow: 0 2px 10px 0 rgba(34,60,80,0.2);
  }
}
</style>