<template>
  <div>
    <h1>Vista Heart Cannons and Bombs</h1>
    <GameIntroduction />
    <GameCard card-type="Heart" />
  </div>
</template>

<script setup lang="ts">
import GameCard from '@/components/games/heartsCannonsBombs/GameCard.vue'
import GameIntroduction from '@/components/games/heartsCannonsBombs/GameIntroduction.vue'

interface item {
  name: string
}
</script>
