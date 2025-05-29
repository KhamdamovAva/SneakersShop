<script setup>
import Card from '../components/Card.vue'

const onClickAdd = () => {
  alert('Добавить!')
}
</script>

<template>
  <div class="grid grid-cols-4 gap-5">
    <Card
      title="Мужские Кроссовки Nike Blazer Mid Suede"
      imgUrl="/images/sneakers/sneakers-1.jpg"
      :price="5000"
      :isFavorite="false"
      :onClickAdd="onClickAdd"
    />
    <!-- <Card
      title="Мужские Кроссовки Nike Air Max 270"
      imgUrl="/images/sneakers/sneakers-2.jpg"
      :price="12000"
    /> -->
  </div>
</template>
