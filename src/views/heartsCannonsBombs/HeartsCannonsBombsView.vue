<template>
  <div class="h-screen w-screen flex flex-col justify-center items-center overflow m-3">
    <!-- Título y componente introductorio -->
    <h1 class="text-2xl font-bold">Vista Heart Cannons and Bombs</h1>
    <GameIntroduction />

    <!-- Grid dinámico -->
    <div class="gameBoard">
      <div :class="`grid grid-cols-${columns.length + 1} gap-2 `">
        <!-- Espacio vacío en la esquina superior izquierda -->
        <div></div>

        <!-- Nombres de las columnas -->
        <div
          v-for="(column, index) in columns"
          :key="'column-' + index"
          class="text-center font-bold bg-slate-600 py-2"
        >
          {{ column }}
        </div>

        <!-- Filas y celdas de las tarjetas -->
        <div v-for="(row, rowIndex) in rows" :key="'row-' + rowIndex" class="contents">
          <!-- Nombre de la fila -->
          <div class="font-bold text-center bg-red-300">{{ row }}</div>

          <!-- Tarjetas (GameCard) -->
          <div
            v-for="(column, columnIndex) in columns"
            :key="'card-' + rowIndex + '-' + columnIndex"
            class="flex justify-center items-center"
          >
            <GameCard :card-type="getCardType(rowIndex, columnIndex)" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import GameCard from '@/components/games/heartsCannonsBombs/GameCard.vue'
import GameIntroduction from '@/components/games/heartsCannonsBombs/GameIntroduction.vue'

const columns = ['Columna 1', 'Columna 2', 'Columna 3']
const rows = ['Fila 1', 'Fila 2', 'Fila 3']

enum CardTypes {
  cannon = 'CANNON',
  bomb = 'BOMB',
  heart = 'HEART'
}

// Función para determinar el tipo de tarjeta basado en la posición (puedes personalizarla)
function getCardType(rowIndex: number, columnIndex: number): string {
  if (rowIndex % 2 === 0 && columnIndex % 2 === 0) {
    return CardTypes.heart
  } else if (rowIndex % 2 === 1) {
    return CardTypes.bomb
  } else {
    return CardTypes.cannon
  }
}
</script>

<style scoped>
.gameBoard {
  @apply flex-grow w-full md:max-w-screen-sm lg:max-w-screen-sm xl:max-w-screen-md 2xl:max-w-screen-lg px-5 py-2 mr-10;
}
</style>
