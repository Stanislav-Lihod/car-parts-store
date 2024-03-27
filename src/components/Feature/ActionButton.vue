<script setup>
const { type, isActive, onClickChangeStatus } = defineProps({
  type: String,
  isActive: Boolean,
  onClickChangeStatus: Function
});

const active = (e) => {
  e.preventDefault();
  onClickChangeStatus();
  e.target.closest('button').classList.toggle('active');
}
</script>

<template>
  <button @click="active" v-if="type.length > 1" :class="{ 'active': isActive }">
    <img :src="`src/assets/icons/${type}.svg`" :alt="type">
  </button>
</template>

<style lang="less" scoped>
button{
  width: 40px;
  height: 40px;
  border-radius: 4px;
  transition: .3s;
  border: 1px solid #e7e7e7;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgba(0, 0, 0, .04);

  img{
    width: 100%;
    height: 100%;
  }

  &:hover{
    background-color: white;
  }

  &.active{
    background-color: rgba(0, 0, 0, .2);
  }
}
</style>