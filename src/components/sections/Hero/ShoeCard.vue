<template>
  <div
    class="cursor-pointer max-sm:flex-1 border-2 rounded-xl"
    :class="shoeImage === bigShoeImage ? 'border-coral-red' : 'border-transparent'"
    @click="handleClick"
  >
    <div
      class="flex justify-center items-center bg-card bg-center bg-cover sm:w-40 sm:h-40 rounded-xl max-sm:p-4"
    >
      {{ shoeImage.bigshoe }}
      <img
        :src="props.shoeImage.thumbnail"
        alt="a shoe image"
        width="127"
        height="103"
        class="object-contain"
      />
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'
const handleClick = () => {
  if (props.shoeImage.bigshoe !== props.bigShoeImage) {
    changeBigShoeImage(shoeImage.bigshoe)
  }
}
//TODO model-value 2 way binding per fare update del bigShoeImage
const props = defineProps({
  shoeImage: {
    type: Object,
    default: { thumbnail: 'ciao', bigshoe: '' },
  },

  changeBigShoeImage: {
    type: Function,
    required: false,
  },
})
</script>
