<script setup lang="ts">
const items = [
'/img/carousel/BarImg.png',
]
</script>

<template>
  <UCarousel
    v-slot="{ item }"
    class-names
    arrows
    :items="items"
    :ui="{
      item: 'transition-opacity [&:not(.is-snapped)]:opacity-40' //basis-[70%]
    }"
    class="mx-auto max-w-sm"
  >
    <img :src="item" width="1000" height="1000" class="rounded-xl">
  </UCarousel>
</template>