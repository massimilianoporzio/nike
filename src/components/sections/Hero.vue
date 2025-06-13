<script setup>
import NikeButton from '../NikeButton.vue'
import { arrowRight } from '@/assets/icons'
</script>

<template>
  <section
    id="home"
    class="flex justify-center w-full min-h-screen gap-10 xl:flex-row max-container"
  >
    <div
      class="relative flex flex-col items-start justify-center w-full xl:w-2/5 max-xl:padding-x pt-28"
    >
      <p>Our Summer Collection</p>
      <h1>
        <span>The New Arrival</span><br />
        <span>Nike</span>
        Shoes
      </h1>
      <p>Discover stylish Nike arrivals, quality comfort, and innovation for your active life.</p>
      <NikeButton :iconURL="arrowRight" label="Shop Now" />
    </div>
  </section>
</template>
