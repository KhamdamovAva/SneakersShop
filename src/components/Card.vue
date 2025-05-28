<script setup>
import like from '../../public/icons/like-1.svg'
import sneaker1 from '../../public/images/sneakers/sneakers-1.jpg'
import Plus from '../../public/icons/plus.svg'
</script>
<template>
  <div
    class="relative bg-white border-slate-100 rounded-3xl p-8 cursor-pointer transition hover:-translate-y-2 hover:shadow-xl"
  >
    <img class="absolute top-8 left-8" :src="like" alt="Like" />
    <img :src="sneaker1" alt="Sneaker" />
    <p class="mt-2">Мужские Кроссовки Nike Blazer Mid Suede</p>

    <div class="flex justify-between mt-5">
      <div class="flex flex-col">
        <span class="text-slate-400">Цена</span>
        <b>1205 руб.</b>
      </div>
      <img :src="Plus" alt="Plus" />
    </div>
  </div>
</template>
