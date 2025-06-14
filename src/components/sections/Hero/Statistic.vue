<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  label: {
    type: String,
    required: true,
  },
  value: {
    type: [String, Number],
    required: true,
  },
})
</script>

<template>
  <div class="">
    <p class="text-4xl font-palanquin font-bold">{{ value }}</p>
    <p class="leading-7 font-montserrat text-slate-gray">{{ label }}</p>
  </div>
</template>
