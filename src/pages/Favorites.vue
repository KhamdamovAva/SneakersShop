<script setup>
import { onMounted, ref } from 'vue'
import axios from 'axios'
import CardList from '../components/CardList.vue'
const favorites = ref([])
onMounted(async () => {
  try {
    const { data } = await axios.get(
      'https://015389e9b582cf1a.mokky.dev/favorites?_relations=items',
    )
    favorites.value = data.map((obj) => obj.item)
  } catch (error) {
    console.log(error)
  }
})
</script>
<template>
  <h2 class="text-3xl font-bold mb-8">Мои Закладки</h2>

  <CardList :items="favorites" is-favorites />
</template>
