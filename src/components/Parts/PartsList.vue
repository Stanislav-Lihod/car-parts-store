<script setup>
import PartCard from "@/components/Parts/PartCard.vue";
import Select from '@/components/Feature/Select.vue'
import Pagination from '@/components/Feature/Pagination.vue'

defineProps({
  items: Array,
  totalCount: Number,
  numberPages: Number,
  currentPage: Number,
  changeOption: Function,
  changePage: Function,
  isLoading: Boolean
})

const sortBy = [{
  name: 'Standart',
  value: 'default'
}, {
  name: 'Lowest price',
  value: 'price'
}, {
  name: 'Highest price',
  value: '-price'
}]
</script>

<template>
  <div class="items" :class="isLoading && 'loading'">
    <div class="sorting">
      <div class="sorting__text">
        We found in the warehouse <span>{{totalCount}}</span> parts:
      </div>
      <div class="sorting__wrapper">
        <Select @change="changeOption" :options="sortBy"/>
      </div>
    </div>
    <PartCard
      v-for="item in items"
      :key="item.part_id"
      :title="item.part_name"
      :part-number="[item.manufacturer_code, item.visible_code, item.other_code]"
      :image="item.image.full"
      :fee="true"
      :seller="item.scrapheap.title"
      :car="item.description"
      :location="[item.scrapheap.country, item.scrapheap.city]"
      :delivery="item.delivery_price"
      :price="item.price_final"
      :isFavorite="false"
      :inBasket="false"
    />
    <Pagination
      :number-page="numberPages"
      :current-page="currentPage"
      @click="changePage"
    />
  </div>
</template>

<style lang="less" scoped>
.items{
  transition: .3s;

  &.loading{
    opacity: .3;
  }
}


.sorting{
  padding: 20px 0;
  display: flex;
  justify-content: space-between;
  gap: 16px;
  align-items: center;

  &__text{
    span{
      font-weight: 700;
    }
  }
}
</style>