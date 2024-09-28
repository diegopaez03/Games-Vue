<template>
  <div>
    <h1>{{ cardImage }}</h1>
  </div>
</template>

<script setup lang="ts">
const props = defineProps<{
  cardType: string
}>()

let cardImage: string = 'Default'

switch (props.cardType) {
  case 'Bomb':
    cardImage = 'BombImage'
    break
  case 'Cannon':
    cardImage = 'CannonImage'
    break
  case 'Heart':
    cardImage = 'HeartImage'
    break
}
</script>
