<script setup>
import DrawerHead from './DrawerHead.vue'
import CartItemList from './CartItemList.vue'

const emit = defineEmits(['createOrder'])

defineProps({
  totalPrice: Number,
  vatPrice: Number
})
</script>

<template>
  <div class="fixed top-0 left-0 h-full w-full bg-black z-10 opacity-70"></div>
  <div class="bg-white w-96 h-full fixed top-0 right-0 z-20 p-8">
    <DrawerHead />
    <CartItemList />

    <div class="flex flex-col gap-4 mt-7">
      <div class="flex gap-2">
        <span>Итого:</span>
        <div class="flex-1 border-dashed border-b"></div>
        <b>{{ totalPrice }} ₽</b>
      </div>

      <div class="flex gap-2">
        <span>Налог 5%</span>
        <div class="flex-1 border-dashed border-b"></div>
        <b>{{ vatPrice }} ₽</b>
      </div>
      <button
        :disabled="totalPrice ? false : true"
        @click="emit('createOrder')"
        class="mt-4 bg-lime-500 disabled:bg-slate-400 cursor-pointer w-full p-3 rounded-xl text-white hover:bg-lime-600 active:bg-lime-700 transition"
      >
        Оформить заказ
      </button>
    </div>
  </div>
</template>
