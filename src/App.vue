<script setup>
  import Header from "@/components/Header.vue";
  import Breadcrumbs from "@/components/Breadcrumbs.vue";
  import PartsList from "@/components/Parts/PartsList.vue";
  import RightModal from "@/components/Modal/RightModal.vue";
</script>

<template>
  <RightModal/>
  <Header/>
  <div class="container">
    <Breadcrumbs/>

    <div class="general">
      <aside></aside>
      <main>
        <PartsList/>
      </main>
    </div>
  </div>
</template>

<style scoped>

.general{
  display: flex;
  gap: 24px;
}

aside{
  background-color: aliceblue;
  flex-basis: 30%;
  min-width: 290px;
}

main{
  flex-basis: 70%;
}
</style>
