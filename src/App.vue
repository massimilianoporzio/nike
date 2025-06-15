<script setup>
import { RouterView } from 'vue-router'
import Nav from '@/components/Nav.vue'
</script>

<template>
  <main class="relative">
    <Nav class="z-50" />

    <RouterView />
  </main>
</template>
