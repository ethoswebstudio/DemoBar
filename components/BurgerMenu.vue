<template>
  <Transition name="slide-fade">
    <aside v-if="visible" class="fixed inset-0 z-50 flex">
      <!-- Overlay -->
      <button class="absolute inset-0 bg-black/60 backdrop-blur-sm" @click="$emit('close')" />

      <!-- Panel -->
      <nav
        class="relative ml-auto h-full w-4/5 max-w-xs flex flex-col
               bg-gradient-to-b from-neutral-900/95 via-neutral-800/95 to-neutral-900/95
               backdrop-blur-xl shadow-2xl border-l border-white/10
               px-6 py-8 gap-10 text-white z-100"
      >
        <!-- Header -->
        <div class="flex items-center justify-between">
          <p class="text-subt font-bold">DemoBar&nbsp;66</p>
          <UButton icon="mdi:close" variant="ghost" size="lg" color="neutral" @click="$emit('close')" />
        </div>

        <!-- Nav links -->
        <ul class="flex flex-col gap-8 text-lg font-semibold">
          <li v-for="item in items" :key="item.label">
            <component
              :is="item.href.startsWith('/') ? 'NuxtLink' : 'a'"
              :to="item.href.startsWith('/') ? item.href : undefined"
              :href="item.href.startsWith('/') ? undefined : item.href"
              @click="$emit('close')"
              class="group flex items-center justify-between hover:text-amber-400"
            >
              {{ item.label }}
              <Icon name="mdi:chevron-right" class="text-xl transition-transform group-hover:translate-x-1" />
            </component>
          </li>
        </ul>

        <p class="mt-auto pt-6 text-center text-xs text-gray-400">
          © {{ new Date().getFullYear() }} DemoBar 66
        </p>
      </nav>
    </aside>
  </Transition>
</template>

<script setup lang="ts">
interface NavItem { label: string; href: string }
defineProps<{ visible: boolean; items: NavItem[] }>()
defineEmits<{ (e:'close'):void }>()
</script>

<style scoped>
.slide-fade-enter-from,
.slide-fade-leave-to { transform: translateX(100%); opacity: 0; }
.slide-fade-enter-to,
.slide-fade-leave-from { transform: translateX(0); opacity: 1; }
.slide-fade-enter-active,
.slide-fade-leave-active { transition: all .35s cubic-bezier(.22,1,.36,1); }
</style>