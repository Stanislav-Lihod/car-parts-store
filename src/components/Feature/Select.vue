<script setup>
  defineProps({
    options: Array
  })
</script>

<template>
  <select>
    <option
      v-for="(option, index) in options"
      :key="{index}"
      :value="option.value"
    >
      {{option.name}}
    </option>
  </select>
</template>

<style lang="less" scoped>
select{
  padding: 12px 16px;
  border-radius: 4px;
}
</style>