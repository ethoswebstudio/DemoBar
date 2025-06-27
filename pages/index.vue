<template>
  <main id="Homepage" class="relative bg-white text-gray-800">

    <!-- ===================================================== -->
    <!-- HERO / LANDING                                        -->
    <!-- ===================================================== -->
    <section
      id="Landing"
      class="relative isolate flex flex-col lg:flex-row items-center justify-center section-px section-py"
    >
      <div class="text-center space-y-3">
        <h1 class="text-megat text-shadow-lg/20">
          <span class="text-xltitle block">Gruppo</span>
          DemoBar
          <span class="block">66</span>
        </h1>
        <p class="text-desc">Vieni a scoprire il nostro mondo</p>
      </div>
    </section>

    <!-- ===================================================== -->
    <!-- SEZIONE CARD LOCALI                                   -->
    <!-- ===================================================== -->
    <section id="DemoBarBistro" class="section-px section-py">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6 xl:gap-10 text-white px-4 py-4 md:px-10 md:py-10">
        <div
          v-for="card in cards"
          :key="card.label"
          :class="[
            'rounded-2xl shadow-lg transition transform duration-300 ease-out hover:scale-105 flex flex-col overflow-hidden',
            card.base, card.hover
          ]"
        >
          <NuxtImg
            :src="card.src"
            :alt="card.alt"
            class="w-auto h-56 object-contain mx-auto"
          />
          <div class="p-4 flex flex-col items-center gap-4">
            <UButton
              :to="card.link"
              class="bg-amber-300 text-black rounded-2xl px-4 py-2 hover:bg-amber-400"
            >
              Scopri il locale
            </UButton>
          </div>
        </div>
      </div>
    </section>

  </main>
</template>

<script setup lang="ts">
interface CardData {
  label: string
  src: string
  alt: string
  base: string
  hover: string
  link: string  
}

const cards: CardData[] = [
  {
    label: 'Bistrò',
    src: '/img/home/BlockBistroMob.png',
    alt: 'Bistrò',
    base: 'bg-emerald-800',
    hover: 'hover:bg-emerald-900',
    link: '/demo77-bistro'
  },
  {
    label: 'Beach',
    src: '/img/home/BlockBeachMob.png',
    alt: 'Beach',
    base: 'bg-fuchsia-800',
    hover: 'hover:bg-fuchsia-900',
    link: '/demo77-beach'
  },
  {
    label: 'Bay',
    src: '/img/home/BlockBayMob.png',
    alt: 'Bay',
    base: 'bg-rose-900',
    hover: 'hover:bg-rose-950',
    link: '/demo77-bay'
  }
]
</script>

<style scoped>
/* section-px / section-py sono già definiti in main.css */
/* text-megat / text-xltitle / text-desc sono utility custom esistenti */

.text-shadow-lg\/20 {
  text-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
}

.zoom-fade-enter-active,
.zoom-fade-leave-active {
  transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1);
}
.zoom-fade-enter-from,
.zoom-fade-leave-to {
  opacity: 0;
  transform: scale(0.96);
}
</style>