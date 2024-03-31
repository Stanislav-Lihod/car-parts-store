<script setup>
import { onMounted, reactive, ref, watch } from 'vue'
  import axios from 'axios'

  import Header from "@/components/Header.vue";
  import Breadcrumbs from "@/components/Breadcrumbs.vue";
  import PartsList from "@/components/Parts/PartsList.vue";
  import RightModal from "@/components/Modal/RightModal.vue";

  const items = ref([])
  const totalCount = ref(0)
  const isLoading = ref(false)
  const filters = reactive({
    page: 1,
    sortBy: 'default',
    searchField: ''
  })
  const paginationPages = ref(1)

  const changeOption = (e) =>{
    filters.sortBy = e.target.value
  }
  const changeSearchField = (e) =>{
    filters.searchField = e.target.value
  }
  const changePage = (e) =>{
    filters.page = Number(e.target.textContent)
  }

  const fetchRequest = async ()=>{
    const params = {
      sortBy: filters.sortBy,
      page: filters.page
    }

    if (filters.searchField){
      params.visible_code = `*${filters.searchField}*`
    }

    try {
      isLoading.value = true
      const { data } = await axios.get('https://9aaca2b44dbb58a9.mokky.dev/parts', { params })

      items.value = data.items
      totalCount.value = data.meta.total_items
      paginationPages.value = data.meta.total_pages

      isLoading.value = false
    }catch (e){
      console.error(e)
    }
  }

  onMounted(fetchRequest)
  watch(filters, fetchRequest)

</script>

<template>
<!--  <RightModal/>-->
  <Header :search-change="changeSearchField"/>
  <div class="container">
    <Breadcrumbs/>

    <div class="general">
      <aside></aside>
      <main>
        <PartsList
          :isLoading="isLoading"
          :items="items"
          :totalCount="totalCount"
          :numberPages="paginationPages"
          :currentPage="filters.page"
          :change-option="changeOption"
          :change-page="changePage"
        />
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
