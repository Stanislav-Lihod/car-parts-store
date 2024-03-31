<script setup>
defineProps({
  numberPage: Number,
  currentPage: Number
})
</script>

<template>
  <div class="pagination">
    <div
      v-for="number in numberPage"
      :key="number"
      :value="number"
      class="pagination__item"
      :class="{'active' : currentPage === number}"
    >
      {{ number }}
    </div>
  </div>
</template>

<style lang="less" scoped>
.pagination{
  display: flex;
  gap: 8px;

  &__item{
    cursor: pointer;
    padding: 12px;
    border: 1px solid rgba(0,0,0,0.2);
    transition: .3s;
    border-radius: 4px;
    min-width: 30px;
    text-align: center;

    &:hover, &.active{
      border: 1px solid rgba(0,0,0,0.3);
      background-color: rgba(0,0,0,0.1);
    }
  }
}
</style>