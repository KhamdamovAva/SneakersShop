<script setup>
import logo from '../../public/images/logo.png'
import Cart from '../../public/icons/cart.svg'
import Heart from '../../public/icons/heart.svg'
import Profile from '../../public/icons/profile.svg'
</script>

<template>
  <header class="flex justify-between border-b border-slate-300 px-10 py-8">
    <div class="flex items-center gap-4">
      <img class="w-10" :src="logo" alt="Logo" />
      <div>
        <h2 class="font-bold text-xl uppercase">Vue Sneakers</h2>
        <p class="text-slate-400">Магазин лучших кроссовок</p>
      </div>
    </div>
    <ul class="flex items-center gap-10">
      <li class="flex items-center gap-3 text-gray-500 hover:text-black cursor-pointer">
        <img :src="Cart" alt="Cart" />
        <b>1205 руб.</b>
      </li>
      <li class="flex items-center gap-3 text-gray-500 hover:text-black cursor-pointer">
        <img :src="Heart" alt="Heart" />
        <span>Закладки</span>
      </li>
      <li class="flex items-center gap-3 text-gray-500 hover:text-black cursor-pointer">
        <img :src="Profile" alt="Profile" />
        <span>Профиль</span>
      </li>
    </ul>
  </header>
</template>
