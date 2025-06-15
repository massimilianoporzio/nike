<script setup>
import NikeButton from '@/components/NikeButton.vue'
import { arrowRight } from '@/assets/icons'
import { bigShoe1, bigShoe2, bigShoe3 } from '@/assets/images'
import { statistics, shoes } from '@/constants'
import Statistic from './Statistic.vue'
import ShoeCard from './ShoeCard.vue'
import { ref } from 'vue'
const bigShoeModel = ref(bigShoe1)
</script>

<template>
  <section
    id="home"
    class="flex justify-center w-full min-h-screen gap-10 xl:flex-row flex-col max-container"
  >
    <div class="relative flex flex-col items-start justify-center w-full xl:w-2/5 padding-x pt-28">
      <p class="text-xl font-montserrat text-coral-red">Our Summer Collection</p>

      <h1 class="mt-10 font-palanquin text-8xl max-sm:text-[72px] max-sm:leading-[82] font-bold">
        <span class="xl:bg-white xl:whitespace-nowrap relative z-10 pr-10">The New Arrival</span>
        <br />
        <span class="text-coral-red inline-block mt-3">Nike</span> Shoes
      </h1>
      <p class="text-slate-gray font-montserrat text-xl leading-8 mt-6 mb-14 sm:max-w-sm">
        Discover stylish Nike arrivals, quality comfort, and innovation for your active life.
      </p>
      <NikeButton :iconURL="arrowRight" label="Shop Now" />
      <div class="flex justify-start items-center w-full flex-wrap mt-20 gap-16">
        <Statistic
          v-for="stat in statistics"
          :key="stat.label"
          :label="stat.label"
          :value="stat.value"
        />
      </div>
    </div>
    <div
      class="relative flex-1 flex justify-center items-center xl:min-h-screen max-xl:py-40 bg-primary bg-hero bg-coverr bg-center"
    >
      <img
        :src="bigShoeModel"
        alt="shoe collection"
        width="610"
        height="500"
        class="object-contain relative z-10"
      />
      <div class="flex sm:gap-6 gap-4 absolute -bottom-[5%] sm:left-[10%] max-sm:px-6">
        <ShoeCard
          v-for="shoe in shoes"
          :key="shoe.thumbnail"
          :shoeImage="shoe"
          v-model:bigShoeModel="bigShoeModel"
        />
      </div>
    </div>
  </section>
</template>
