<template>
  <nav
    :class="[
      'fixed top-4 inset-x-4 z-50 px-4 md:px-6 xl:px-8 py-2 md:py-3',
      'flex justify-between items-center rounded-3xl transition',
      /* sfondo/blur SOLO dopo il primo pixel */
      isScrolled ? 'backdrop-blur-md bg-white/10 shadow-md' : 'bg-transparent'
    ]"
  >
    <!-- Logo -->
    <ULink to="/" aria-label="DemoBar 66 Home" class="flex items-center gap-2">
      <img
        src="/img/home/Logo.png"
        alt="Logo DemoBar 66"
        class="w-10 h-10 md:w-12 md:h-12 xl:w-16 xl:h-16"
      />
      <span class="sr-only">DemoBar 66</span>
    </ULink>

    <!-- Desktop nav -->
    <ul class="hidden xl:flex items-center gap-10 font-semibold text-subt">
      <li><a href="#DemoBarBistro" class="nav-link">I locali</a></li>
      <li><a href="#Map"           class="nav-link">Dove siamo</a></li>
      <li><a href="#footer"      class="nav-link">Contatti</a></li>
    </ul>

    <!-- Burger -->
    <button
      @click="openMenu = true"
      class="xl:hidden text-4xl nav-link w-10 h-10 flex items-center justify-center"
      aria-label="Apri menu"
    >
      <Icon name="mdi:menu" />
    </button>
  </nav>

  <ClientOnly>
    <BurgerMenu
      :visible="openMenu"
      :locali="locali"
      :current="current"
      @close="openMenu = false"
    />
  </ClientOnly>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import BurgerMenu from './BurgerMenu.vue'

/* stato */
const openMenu   = ref(false)
const isScrolled = ref(false)

/* lista locali */
const locali = [
  { label: 'Bistrò', value: 'bistro', link: '/demo77-bistro' },
  { label: 'Beach',  value: 'beach',  link: '/demo77-beach'  },
  { label: 'Bay',    value: 'bay',    link: '/demo77-bay'    }
]
const current = ref(locali[0])

/* blur solo quando scrollY > 0 */
function handleScroll () {
  isScrolled.value = window.scrollY > 0
}
onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<style scoped>
nav { transition-property: background-color, backdrop-filter; }
.nav-link { color: #000000; transition: color .2s; }
.nav-link:hover { color: #fbbf24; }
</style>