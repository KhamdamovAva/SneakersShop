<script setup>
import like from '/icons/like-1.svg'
import like2 from '/icons/like-2.svg'
import Plus from '/icons/plus.svg'
import Checked from '/icons/checked.svg'

defineProps({
  imgUrl: String,
  title: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickAdd: Function,
  onClickFavorite: Function,
})
</script>
<template>
  <div
    class="relative bg-white border-slate-100 rounded-3xl p-8 cursor-pointer transition hover:-translate-y-2 hover:shadow-xl"
  >
    <img
      @click="onClickFavorite"
      class="absolute top-8 left-8"
      :src="!isFavorite ? like : like2"
      alt="Like"
    />
    <img :src="imgUrl" alt="Sneaker" />
    <p class="mt-2">{{ title }}</p>

    <div class="flex justify-between mt-5">
      <div class="flex flex-col">
        <span class="text-slate-400">Цена</span>
        <b>{{ price }} руб.</b>
      </div>
      <img @click="onClickAdd" :src="!isAdded ? Plus : Checked" alt="Plus" />
    </div>
  </div>
</template>
