<script setup>
import logo from '/images/logo.png'
import Cart from '/icons/cart.svg'
import Heart from '/icons/heart.svg'
import Profile from '/icons/profile.svg'

const emit = defineEmits(['openDrawer'])

defineProps({
  totalPrice: Number,
})
</script>

<template>
  <header class="flex justify-between border-b border-slate-200 px-10 py-8">
    <router-link to="/">
      <div class="flex items-center gap-4">
        <img class="w-10" :src="logo" alt="Logo" />
        <div>
          <h2 class="font-bold text-xl uppercase">Vue Sneakers</h2>
          <p class="text-slate-400">Магазин лучших кроссовок</p>
        </div>
      </div>
    </router-link>

    <ul class="flex items-center gap-10">
      <li
        @click="() => emit('openDrawer')"
        class="flex items-center gap-3 text-gray-500 hover:text-black cursor-pointer"
      >
        <img :src="Cart" alt="Cart" />
        <b>{{ totalPrice }} руб.</b>
      </li>

      <router-link to="/favorites">
        <li class="flex items-center gap-3 text-gray-500 hover:text-black cursor-pointer">
          <img :src="Heart" alt="Heart" />
          <span>Закладки</span>
        </li>
      </router-link>

      <li class="flex items-center gap-3 text-gray-500 hover:text-black cursor-pointer">
        <img :src="Profile" alt="Profile" />
        <span>Профиль</span>
      </li>
    </ul>
  </header>
</template>
