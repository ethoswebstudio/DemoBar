<template>
  <footer id="footer" class="bg-white text-gray-800">
    <!-- TOP -->
    <div
      class="max-w-7xl mx-auto px-4 sm:px-8 py-12 grid gap-10
             md:grid-cols-3 md:gap-16 lg:gap-24"
    >
      <!-- Brand + Social -->
      <div class="space-y-3 flex flex-col items-center">
        <div class="flex items-center gap-4">
          <img src="/img/home/Logo.png" alt="DemoBar 66" class="w-12 h-12" />
          <p class="text-subt">DemoBar 66</p>
        </div>

        <p class="text-sm text-gray-400">
          Il gruppo che unisce<br />Bistrò, Beach e Bay.
        </p>

        <div class="flex gap-4 text-2xl">
          <ULink to="https://instagram.com/demobar66" target="_blank" aria-label="Instagram">
            <Icon name="mdi:instagram" class="hover:text-amber-400 transition" />
          </ULink>
          <ULink to="https://facebook.com/demobar66group" target="_blank" aria-label="Facebook">
            <Icon name="mdi:facebook" class="hover:text-amber-400 transition" />
          </ULink>
        </div>
      </div>

      <!-- Contatti -->
      <div class="space-y-4 flex flex-col items-center">
        <h3 class="text-subt text-gray-800">Contatti</h3>
        <ul class="text-sm space-y-2">
          <li class="flex items-center gap-2">
            <Icon name="mdi:phone" /><ULink to="tel:+390490991513">049&nbsp;099&nbsp;1513</ULink>
          </li>
          <li class="flex items-center gap-2">
            <Icon name="mdi:cellphone" /><ULink to="tel:+39339749372">393&nbsp;974&nbsp;9372</ULink>
          </li>
          <li class="flex items-center gap-2 break-all">
            <Icon name="mdi:email" /><ULink to="mailto:info@demobar66.it">info@demobar66.it</ULink>
          </li>
        </ul>
      </div>

      <!-- Policy -->
      <div class="space-y-4 flex flex-col items-center">
        <h3 class="text-subt text-gray-800">Documenti</h3>
        <ul class="text-sm space-y-2">
          <li><ULink to="/privacy" class="hover:text-amber-400">Privacy Policy</ULink></li>
          <li><ULink to="/cookies" class="hover:text-amber-400">Cookie Policy</ULink></li>
        </ul>
      </div>
    </div>

    <!-- BOTTOM -->
    <div class="border-t border-white/10 text-center py-6 text-xs text-gray-400">
      © {{ new Date().getFullYear() }} DemoBar 66. Tutti i diritti riservati.
    </div>
  </footer>
</template>

<script setup lang="ts">
// nessuna logica necessaria
</script>