<script setup>
import { headerLogo } from '@/assets/images'
import { hamburger } from '@/assets/icons'
import { navLinks } from '../constants'
import { ref } from 'vue'
var isOpen = ref(false)
</script>
<template>
  <header class="padding-x py-8 absolute z-10 w-full">
    <nav class="flex items-center justify-between max-container">
      <a href="/">
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
        <a href="/">Explore now</a>
      </div>
      <div class="max-lg:flex flex-col items-center justify-center hidden">
        <img :src="hamburger" alt="Hamburger Menu" width="25" height="25" />
        <div class="bg-sky-50 w-50 h-full mt-2">
          <ul class="text-center my-3">
            <li v-for="link in navLinks" :key="link.label" class="mb-3">
              <a
                href="#"
                v-scroll-to="link.href"
                class="font-montserrat leading-normal text-lg text-slate-gray"
              >
                {{ link.label }}
              </a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
</template>
