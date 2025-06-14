<script setup>
import { computed, inject, ref } from 'vue'
import CartItemList from './CartItemList.vue'
import nextIcon from '/icons/blackArrow-next.svg'
import InfoContent from './InfoContent.vue'
import box from '/icons/box.svg'
import check from '/icons/check.svg'
import axios from 'axios'

const emit = defineEmits(['createOrder'])

const props = defineProps({
  totalPrice: Number,
  vatPrice: Number,
})
const { cart, closeDrawer } = inject('cart')

const isCreatingOrder = ref(false)
const orderId = ref(null)

const createOrder = async () => {
  try {
    isCreatingOrder.value = true

    const { data } = await axios.post(`https://015389e9b582cf1a.mokky.dev/orders`, {
      items: cart.value,
      totalPrice: props.totalPrice.value,
    })

    cart.value = []

    orderId.value = data.id
  } catch (error) {
    console.log(error)
  } finally {
    isCreatingOrder.value = false
  }
}
const cartIsEmpty = computed(() => cart.value.length === 0)

const buttonDisabled = computed(() => isCreatingOrder.value || cartIsEmpty.value)
</script>

<template>
  <div class="fixed top-0 left-0 h-full w-full bg-black z-10 opacity-70"></div>
  <div class="bg-white w-96 h-full fixed right-0 top-0 z-20 p-8">
    <div class="flex items-center gap-5 mb-5">
      <img
        @click="closeDrawer"
        class="opacity-30 cursor-pointer rotate-180 hover:opacity-100 transition hover:-translate-x-1"
        :src="nextIcon"
        alt="Arrow icon"
      />
      <h2 class="text-2xl font-bold">Корзина</h2>
    </div>

    <div v-if="!totalPrice || orderId" class="flex h-full items-center">
      <InfoContent
        v-if="!totalPrice && !orderId"
        title="Корзина пустая"
        description="Добавьте хотя бы одну пару кроссовок, чтобы сделать заказ."
        :imageUrl="box"
      />
      <InfoContent
        v-if="orderId"
        title="Заказ оформлен!"
        :description="`Ваш заказ # ${orderId} скоро будет передан курьерской доставке`"
        :imageUrl="check"
      />
    </div>

    <div v-else>
      <CartItemList />

      <div class="flex flex-col gap-4 mt-7">
        <div class="flex gap-2">
          <span>Итого:</span>
          <div class="flex-1 border-b border-dashed"></div>
          <b>{{ totalPrice }} руб.</b>
        </div>
        <div class="flex gap-2">
          <span>Налог 5%:</span>
          <div class="flex-1 border-b border-dashed"></div>
          <b>{{ vatPrice }} руб.</b>
        </div>
        <button
          :disabled="buttonDisabled"
          @click="createOrder"
          class="bg-lime-500 mt-3 w-full rounded-xl py-3 text-white hover:bg-lime-600 transition cursor-pointer active:bg-lime-700 disabled:bg-slate-300"
        >
          Оформить заказ
        </button>
      </div>
    </div>
  </div>
</template>
