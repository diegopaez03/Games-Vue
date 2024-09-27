<template>
  <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-7 bg-slate-700 mb-4 xl:rounded-xl">
    <div class="relative flex h-16 items-center justify-between">
      <div class="hidden sm:ml-2 sm:block">
        <div class="flex space-x-4 text-xl">
          <a
            v-for="route in routes"
            :key="route.name"
            :href="route.path"
            :class="'text-gray-300 hover:bg-gray-800 hover:text-white hover:rounded-md px-2 py-1'"
            >{{ route.name }}</a
          >
        </div>
      </div>

      <h1 class="text-gray-400 text-xl">Diego's App</h1>
    </div>
  </div>
</template>

<script setup lang="ts">
import router from '@/router'

const routes = router.getRoutes()
</script>

<style scoped></style>
