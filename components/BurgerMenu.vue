<template>
  <Transition name="slide-fade">
    <aside v-if="visible" class="fixed inset-0 z-50 flex">
      <!-- overlay -->
      <button
        aria-label="Chiudi menu"
        class="absolute inset-0 bg-black/60 backdrop-blur-sm"
        @click="$emit('close')"
      />

      <!-- panel -->
      <nav
        class="relative ml-auto h-full w-4/5 max-w-xs flex flex-col
               bg-gradient-to-b from-neutral-900/95 via-neutral-800/95 to-neutral-900/95
               backdrop-blur-xl shadow-2xl border-l border-white/10
               px-6 py-8 gap-10 text-white"
      >
        <!-- header -->
        <div class="flex items-center justify-between">
          <p class="text-subt font-bold">DemoBar&nbsp;66</p>
          <UButton
            icon="mdi:close"
            variant="ghost"
            size="lg"
            color="neutral"
            @click="$emit('close')"
          />
        </div>

        <!-- nav link  -->
        <ul class="flex flex-col gap-8 text-lg font-semibold">
          <li><a href="#DemoBarBistro" @click="$emit('close')" class="group hover:text-amber-400">I locali <Icon name="mdi:chevron-right" class="group-hover:translate-x-1" /></a></li>
          <li><a href="#Map"           @click="$emit('close')" class="group hover:text-amber-400">Dove siamo   <Icon name="mdi:chevron-right" class="group-hover:translate-x-1" /></a></li>
          <li><a href="#Partners"      @click="$emit('close')" class="group hover:text-amber-400">Partner      <Icon name="mdi:chevron-right" class="group-hover:translate-x-1" /></a></li>
        </ul>

        <!-- CTA -->
        <div class="mt-auto flex flex-col gap-4">
          <UButton
            :to="`tel:+39${tel[currentLocal.value]}`"
            icon="mdi:phone"
            rounded="full"
            class="w-full bg-amber-500 hover:bg-amber-600 text-black"
          >
            Chiama {{ currentLocal.label }}
          </UButton>
          <UButton
            :to="`mailto:info@demobar66.it?subject=${currentLocal.label}`"
            icon="mdi:mail"
            variant="ghost"
            rounded="full"
            class="w-full hover:bg-amber-400/10 text-amber-400"
          >
            Scrivici
          </UButton>
        </div>

        <p class="pt-6 text-center text-xs text-gray-400">
          © {{ new Date().getFullYear() }} DemoBar 66.
        </p>
      </nav>
    </aside>
  </Transition>
</template>

<script setup lang="ts">
interface Local {
  label: string
  value: string
  link: string
}
const props = defineProps<{
  visible: boolean
  locali: Local[]
  current: Local
}>()
const emit = defineEmits<{ (e: 'close'): void }>()

const currentLocal = ref(props.current)
const locali = props.locali

/* telefono per locale (placeholder) */
const tel: Record<string, string> = {
  bistro: '0451234567',
  beach:  '0541987654',
  bay:    '0811234567'
}
</script>

<style scoped>
.slide-fade-enter-from,
.slide-fade-leave-to { transform: translateX(100%); opacity: 0; }
.slide-fade-enter-to,
.slide-fade-leave-from { transform: translateX(0); opacity: 1; }
.slide-fade-enter-active,
.slide-fade-leave-active { transition: all .35s cubic-bezier(.22,1,.36,1); }
</style>