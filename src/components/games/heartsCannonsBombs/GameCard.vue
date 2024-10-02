<template>
  <div>
    <!-- Contenedor centrado vertical y horizontalmente -->
    <div
      class="bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700 flex flex-col items-center justify-between hover:shadow-2xl aspect-square"
      style="width: 100%"
    >
      <img
        :src="cardImage"
        alt="Imagen de {{ props.cardType }}"
        class="w-11/12 h-auto object-contain mt-4 px-4"
      />

      <!-- Texto de la tarjeta -->
      <h5 class="textPequeno">
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

<style scoped>
.textPequeno {
  @apply text-base sm:text-lg md:text-xl lg:text-2xl font-bold tracking-tight text-gray-900 dark:text-white text-center;
}
</style>
