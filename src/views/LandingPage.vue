<script setup>
import {
  Hero,
  PopularProducts,
  Services,
  CustomerReview,
  Subscribe,
  Footer,
} from '@/components/sections'
</script>

<template>
  <section class="xl:padding-l wide:padding-r padding-b">
    <Hero />
  </section>
  <section class="padding">
    <PopularProducts />
  </section>
  <section class="padding-x py-10">
    <Services />
  </section>
  <section class="padding">SpecialOffers</section>
  <section class="bg-pale-blue padding">
    <CustomerReview />
  </section>
  <section class="padding-x sm:py-32 py-16 w-full">
    <Subscribe />
  </section>
  <section class="bg-black padding-x padding-t pb-8">
    <Footer />
  </section>
</template>
