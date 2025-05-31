<script setup>
import Card from '../components/Card.vue'

defineProps({
  items: Array,
})

const onClickAdd = () => {
  alert('Добавить!')
}
</script>

<template>
  <div class="grid grid-cols-4 gap-5">
    <Card
      v-for="item in items"
      :key="item.id"
      :title="item.title"
      :imgUrl="item.imageUrl"
      :price="item.price"
      :onClickAdd="onClickAdd"
    />
  </div>
</template>
