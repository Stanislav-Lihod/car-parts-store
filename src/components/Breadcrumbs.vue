<script setup>
</script>

<template>
  <ul>
    <li>LSS Garage</li>
    <li>Car make catalog</li>
    <li>Volkswagen</li>
    <li>Multivan</li>
  </ul>
</template>

<style lang="less" scoped>
ul{
  padding: 20px 0 ;
  margin: 0;
  display: flex;
  gap: 8px;
  list-style: none;

  li{
    display: flex;
    align-items: center;

    &:not(:last-child){
      &::after{
        color: #000;
        font: 8px icomoon;
        content: "\e90a";
        margin-left: 8px;
      }
    }
  }
}
</style>