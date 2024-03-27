<script setup>
</script>

<template>
  <header>
    <div class="container">
      <div class="logo">
        <img src="../assets/images/logo.png" alt="logo" class="logo__img">
      </div>

      <div class="menu">
        <div>Wishlist</div>
        <div>Profile</div>
        <div>Basket</div>
      </div>
    </div>
  </header>
</template>

<style lang="less" scoped>
header{
  box-shadow: 0px 10px 20px 0px rgba(34,60,80,0.2);
}

.container{
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
}

.logo{
  &__img{
    max-width: 120px;
  }
}

.menu{
  display: flex;
  gap: 8px 16px;
  font-size: 18px;
  font-weight: 500;
}
</style>