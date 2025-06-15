<template>
  <div
    class="cursor-pointer max-sm:flex-1 border-2 rounded-xl"
    :class="shoeImage.bigShoe === bigShoeModel ? 'border-coral-red' : 'border-transparent'"
    @click="handleClick"
    @mouseover="changeBigShoeImage(shoeImage.bigShoe)"
  >
    <div
      class="flex justify-center items-center bg-card bg-center bg-cover sm:w-40 sm:h-40 rounded-xl max-sm:p-4"
    >
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
import { defineModel } from 'vue'
const bigShoeModel = defineModel('bigShoeModel', {
  type: String,
  required: true,
})
const handleClick = () => {
  console.log(props)
  if (props.shoeImage.bigShoe !== bigShoeModel.value) {
    changeBigShoeImage(props.shoeImage.bigShoe)
  }
}

function changeBigShoeImage(newImage) {
  bigShoeModel.value = newImage
}
//TODO model-value 2 way binding per fare update del bigShoeImage
const props = defineProps({
  shoeImage: {
    type: Object,
    default: { thumbnail: 'ciao', bigshoe: 'ahahah' },
  },
})
</script>
