<script setup>
import Card from './Card.vue'

const onClickAdd = () => {
  alert('Добавить')
}
</script>

<template>
  <div class="grid grid-cols-4 gap-5">
    <Card
      title="Мужские Кроссовки Nike Blazer Mid Suede"
      image-url="/sneakers/sneakers-1.jpg"
      :price="12000"
      :onClickAdd="onClickAdd"
      :onClickFavorite="onClickAdd"
      :isFavorite="true"
    />
  </div>
</template>
