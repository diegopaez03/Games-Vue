<template>
  <div class="h-screen">
    <!-- Contenedor centrado vertical y horizontalmente -->
    <div
      class="max-w-sm w-40 h-40 bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700 flex flex-col items-center justify-between hover:shadow-2xl"
    >
      <!-- Imagen con tamaño fijo -->
      <img
        :src="cardImage"
        alt="Imagen de {{ props.cardType }}"
        class="size-20 object-contain mt-4"
      />

      <!-- Texto de la tarjeta -->
      <h5 class="mb-4 text-3xl font-bold tracking-tight text-gray-900 dark:text-white text-center">
        {{ props.cardType }}
      </h5>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps<{
  cardType: string
}>()

let cardImage: string = '/Warning.png'

switch (props.cardType) {
  case 'BOMB':
    cardImage = '/heartsCannonsBombs/Bomb.png'
    break
  case 'CANNON':
    cardImage = '/heartsCannonsBombs/Cannon.png'
    break
  case 'HEART':
    cardImage = '/heartsCannonsBombs/Heart.png'
    break
}
</script>
