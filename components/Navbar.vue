<template>
  <nav
    :class="[
      'fixed top-0 z-50 flex justify-between items-center w-full px-6 py-3 bg-white',
      /* BARRA TRASPARENTE CON SFONDO BLUR
      'fixed top-4 inset-x-4 z-50 flex justify-between items-center rounded-3xl transition bg-amber-50',
       isScrolled ? 'backdrop-blur-md bg-white/10 shadow-md px-6 py-3'
                 : 'bg-transparent px-4 py-2' */
    ]"
  >
    <!-- Logo -->
    <ULink to="/" aria-label="DemoBar 66 Home" class="flex items-center gap-2">
      <img
        src="/img/home/Logo.png"
        alt="DemoBar 66"
        class="w-10 h-10 md:w-12 md:h-12 xl:w-16 xl:h-16"
      />
      <span class="sr-only">DemoBar 66</span>
    </ULink>

    <!-- Nav desktop (solo XL) -->
    <ul class="hidden xl:flex gap-10 font-semibold text-subt">
      <li
        v-for="item in navItems"
        :key="item.label"
      >

      <component
          :is="item.href.startsWith('/') ? 'NuxtLink' : 'a'"
          :to="item.href.startsWith('/') ? item.href : undefined"
          :href="item.href.startsWith('/') ? undefined : item.href"
          class="nav-link"
        >
          {{ item.label }}
        </component>
      </li>
    </ul>

    <!-- Burger mobile -->
    <button
      @click="openMenu = true"
      class="xl:hidden text-4xl nav-link w-10 h-10 flex items-center justify-center"
      aria-label="Apri menu"
    >
      <Icon name="mdi:menu" />
    </button>
  </nav>

  <ClientOnly>
    <BurgerMenu :visible="openMenu" :items="navItems" @close="openMenu = false" />
  </ClientOnly>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted, computed } from 'vue'
import { useRoute } from 'vue-router'
import BurgerMenu from '@/components/BurgerMenu.vue'

/* blur on scroll ---------------------------------------------------------
const isScrolled = ref(false)
function onScroll () { isScrolled.value = window.scrollY > 0 }
onMounted  (() => addEventListener('scroll', onScroll))
onUnmounted(() => removeEventListener('scroll', onScroll)) */

/* nav items dinamici ----------------------------------------------------- */
const route = useRoute()
interface NavItem { label: string; href: string }
const navItems = computed<NavItem[]>(() => route.meta.navItems as NavItem[] ?? [])

/* burger state ----------------------------------------------------------- */
const openMenu = ref(false)
</script>

<style scoped>
nav { transition-property: background-color, backdrop-filter; }
.nav-link { color: #4a5568; transition: color .2s; }
.nav-link:hover { color: #fbbf24; }
</style>