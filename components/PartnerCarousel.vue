<template>
  <UCarousel
    v-slot="{ item }"
    :items="logos"
    :autoplay="!!autoplay"
    loop
    class="max-w-6xl mx-auto"
    :ui="{
      item: 'basis-1/2 sm:basis-1/3 md:basis-1/5 p-4 flex justify-center'
    }"
  >
    <NuxtImg
      :src="item"
      width="160"
      height="80"
      class="object-contain grayscale hover:grayscale-0 transition"
      :alt="`Logo ${itemAlt(item)}`"
    />
  </UCarousel>
</template>

<script setup lang="ts">
/**
 * props:
 *  - logos: string[]  : array di path immagini
 *  - autoplay: number : ms (0 = nessun autoplay) – default 2500
 */
defineProps<{
  logos: string[]
  autoplay?: number
}>()

/* helper per alt text */
const itemAlt = (src: string) => src.split('/').pop()?.split('.')[0] || 'logo'
</script>