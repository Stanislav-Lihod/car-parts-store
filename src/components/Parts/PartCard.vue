<script setup>
defineProps({
  image: String,
  title: String,
  car: String,
  partNumber: Array,
  price: String,
  fee: Boolean,
  delivery: String,
  seller: String,
  location: Array,
  inBasket: Boolean,
  isFavorite: Boolean
})

import ActionButton from "@/components/Feature/ActionButton.vue";
</script>

<template>
  <div class="card-part">
    <div class="part-image"
         :style="{'background-image': 'url(' + (image || 'src/assets/images/logo.png') + ')'}"></div>
    <div class="part-content">
      <div class="part-content__title" v-if="title">{{ title }}</div>
      <div class="part-content__car" v-if="car">{{car.replace("&lt;br&gt;", ' ')}}</div>
      <div class="part-content__part-number">
        {{ partNumber.join(', ') }}
      </div>
      <div class="part-content__price">{{ price }}</div>
      <div class="part-content__fee" v-if="fee">+ Service Fee</div>
      <div class="part-content__delivery" v-if="delivery">+ Delivery: {{ delivery }}</div>
      <div class="part-content__seller" v-if="seller">{{ seller }}</div>
      <div class="part-content__location" v-if="location">{{ location.join(', ') }}</div>
    </div>
    <div class="actions">
      <ActionButton
          :isActive="inBasket"
          type="basket"
          :on-click-change-status="()=>{inBasket = !inBasket}"
      />
      <ActionButton
          :isActive="isFavorite"
          type="wish"
          :on-click-change-status="()=>{isFavorite = !isFavorite}"
      />
    </div>
  </div>
</template>

<style lang="less" scoped>
.card-part{
  padding: 16px;
  border: 1px solid #e7e7e7;
  border-radius: 4px;
  display: flex;
  gap: 16px;
  align-items: flex-start;
  transition: .3s;

  &:not(:last-child){
    margin-bottom: 16px;
  }

  &:hover{
    background-color: rgba(0, 0, 0, .04);
  }
}

.part-image{
  width: 260px;
  height: 192px;
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  border-radius: 4px;
}

.part-content{
  flex-grow: 1;

  &__title{
    font-weight: 500;
  }

  &__car{
    font-size: 13px;
    color: #666;
  }

  &__part-number{
    font-size: 14px;
    display: flex;
    gap: 8px;
    color: #0b5391;
  }

  &__price{
    margin-top: 16px;
    margin-bottom: 4px;
    font-size: 26px;
    font-weight: 700;
  }

  &__fee, &__delivery{
    font-size: 13px;
  }

  &__seller{
    margin-top: 8px;
    color: #666;
    font-size: 14px;
  }

  &__location{
    color: #666666;
    font-size: 14px;
  }
}

.actions{
  display: flex;
  flex-direction: column;
  align-self: flex-end;
  justify-content: flex-end;
  gap: 8px;
}
</style>