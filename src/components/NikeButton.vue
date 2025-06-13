<template>
  <button
    class="flex items-center justify-center gap-2 py-4 text-lg leading-none text-white transition-colors duration-300 border rounded-full px-7 font-montserrat bg-coral-red border-coral-red"
  >
    {{ label }}
    <img class="w-5 h-5 ml-12 rounded-full" v-if="iconURL" :src="iconURL" alt="arrow right icon" />
  </button>
</template>

<script setup>
const props = defineProps({
  label: {
    type: String,
    default: 'Click Me',
  },
  iconURL: {
    type: String,
    default: '',
  },
})
</script>
