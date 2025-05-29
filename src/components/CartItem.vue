<script setup>
import close from '/icons/close.svg'
defineProps({
  title: String,
  price: Number,
  imageUrl: String,
})
</script>
<template>
  <div class="flex items-center border mb-4 border-slate-200 p-4 rounded-xl gap-4">
    <img class="w-16 h-16" :src="imageUrl" alt="sneaker" />
    <div class="flex flex-col">
      <p class="text-[14px]">{{ title }}</p>

      <div class="flex justify-between mt-2">
        <b>{{ price }} руб.</b>
        <img
          class="opacity-40 hover:opacity-100 cursor-pointer transition"
          :src="close"
          alt="Close button"
        />
      </div>
    </div>
  </div>
</template>
