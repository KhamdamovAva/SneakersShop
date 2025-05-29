<script setup>
import CartItem from './CartItem.vue'
import sneaker from '/images/sneakers/sneakers-1.jpg'
import sneaker2 from '/images/sneakers/sneakers-4.jpg'
</script>
<template>
  <div>
    <CartItem title="Мужские Кроссовки Nike Air Max 270" :price="12999" :imageUrl="sneaker" />
    <CartItem title="Мужские Кроссовки Nike Air Max 270" :price="8490" :imageUrl="sneaker2" />
    <CartItem title="Мужские Кроссовки Nike Air Max 270" :price="12999" :imageUrl="sneaker" />
    <CartItem title="Мужские Кроссовки Nike Air Max 270" :price="8490" :imageUrl="sneaker2" />
  </div>
</template>
