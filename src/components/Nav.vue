<script setup>
import { headerLogo } from '@/assets/images'
import { hamburger } from '@/assets/icons'
import { navLinks } from '@/constants'
import { ref } from 'vue'
var isOpen = ref(false)
</script>
<template>
  <header class="padding-x py-8 absolute z-10 w-full">
    <nav class="flex items-center justify-between max-container">
      <a href="/" class="self-start">
        <img :src="headerLogo" alt="Logo" width="129" height="29" class="m-0 w-[129px] h-[29px]" />
      </a>
      <ul class="flex-1 flex justify-center items-center gap-12 max-lg:hidden mx-3">
        <li v-for="link in navLinks" :key="link.label">
          <a
            href="#"
            v-scroll-to="link.href"
            class="font-montserrat leading-normal text-lg text-slate-gray"
          >
            {{ link.label }}
          </a>
        </li>
      </ul>
      <div
        className="flex gap-2 text-lg leading-normal font-medium font-montserrat max-lg:hidden wide:mr-24"
      >
        <a href="/">Sign in</a>
        <span>/</span>
        <a href="/" class="mr-18">Explore now</a>
      </div>
      <div class="max-lg:flex flex-col items-center justify-center hidden">
        <img
          class="self-start cursor-pointer"
          :src="hamburger"
          alt="Hamburger Menu"
          width="25px"
          height="25px"
          v-if="!isOpen"
          @click="isOpen = !isOpen"
        />
        <svg
          @click="isOpen = !isOpen"
          preserveAspectRatio="xMidYMid meet"
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 22 22"
          stroke-width="1.5"
          stroke="currentColor"
          class="size-7 self-end cursor-pointer"
          v-if="isOpen"
        >
          <path stroke-linecap="round" stroke-linejoin="round" d="M6 18 18 6M6 6l12 12" />
        </svg>
        <div
          class="bg-primary opacity-95 w-60 h-50 mt-2 flex flex-col justify-center items-center"
          v-if="isOpen"
        >
          <ul class="flex flex-col gap-2 z-21 justify-around items-center">
            <li v-for="link in navLinks" :key="link.label">
              <a
                href="#"
                v-scroll-to="link.href"
                class="font-montserrat leading-normal text-lg text-slate-gray"
              >
                {{ link.label }}
              </a>
            </li>
          </ul>
          <div
            className="flex mt-4 gap-2 text-lg leading-normal font-medium font-montserrat max-lg:block wide:mr-24"
          >
            <a href="/">Sign in</a>
            <span>/</span>
            <a href="/">Explore now</a>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>
