<template>
  <main id="Homepage" class="relative bg-white text-gray-800">

    <!-- ===================================================== -->
    <!-- HERO / LANDING                                        -->
    <!-- ===================================================== -->
    <section
      id="Landing"
      class="relative isolate flex flex-col lg:flex-row items-center justify-center padding-px padding-py
        bg-[url('/img/home/landingMob.png')]
        xl:bg-[url('/img/home/landingDsk.png')] 
        bg-no-repeat bg-cover bg-center"
    >
      <div class="text-center space-y-3">
          <p class="font-['poppins'] text-5xl xl:text-7xl  leading-14 xl:leading-28;">Gruppo</p>
          <p class="text-megat text-shadow-lg/20">DemoBar 66</p>
          <p class="text-desc pt-2.5">Il <b>gruppo</b> DemoBar 66 nasce per offrire un'esperienza gastronomica <b>unica</b>, combinando <b>tradizione</b> e <b>innovazione</b>.
            Ci impegniamo a creare un'<b>atmosfera accogliente</b> e <b>raffinata</b>, dove ogni dettaglio conta.
            Scopri i nostri locali e lasciati conquistare. <b>Enjoy</b></p>
      </div>
    </section>

    <!-- ===================================================== -->
    <!-- SEZIONE CARD LOCALI                                   -->
    <!-- ===================================================== -->
    <section id="DemoBarBistro" class="padding-px grid grid-cols-1 gap-6 xl:gap-10 bg-amber-50 padding-px padding-py">
        <div
          v-for="card in cards"
          :key="card.label"
          :class="[
            'rounded-2xl shadow-lg transition transform duration-300 ease-out hover:scale-105 flex flex-col overflow-hidden relative',
            card.base, card.hover
          ]"
        >
          <NuxtImg
            :src="card.src"
            :alt="card.alt"
            class="w-auto h-56 object-contain mx-auto z-20"
          />
            <!--<div class="z-10 ellipse absolute inset-0"></div>-->
          <div class="p-4 flex flex-col items-center gap-4">
            <UButton
              :to="card.link"
              class="bg-amber-300 text-shadow-gray-700 text-btn rounded-lg px-4 py-2 hover:bg-amber-400 z-20"
            >
              Scopri il locale
            </UButton>
          </div>
        </div>
    </section>

    <!-- ===================================================== -->
    <!-- Partners                                               -->
    <!-- ===================================================== -->
    <section id="Partners" class="padding-px padding-py">
      <div class="mb-10">
        <h2 class="text-title">I nostri Partners</h2>
        <p class="text-desc">Collaboriamo con i migliori per offrirti un'esperienza unica</p>
      </div>
        <PartnerCarousel :logos="partnerLogos" :autoplay="100" />
    </section>


    <!-- ===================================================== -->
    <!-- MAPPA                                               -->
    <!-- ===================================================== -->
    <section id="Map" 
                 class="padding-px padding-py bg-amber-50">
        <div class="mb-10">
            <h2 class="text-title">Dove siamo</h2>
            <p class="text-desc">Scopri la nostra posizione e raggiungici facilmente</p>
        </div>
        <div class="h-72 xl:h-96 mb-10">
            <iframe
            title="Mappa – DemoBar66"
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade"
            src="https://www.google.com/maps/embed?pb=…"
            class="w-full h-full rounded-xl shadow-lg border-0"
            ></iframe>
        </div>

        <!-- CARD INDIRIZZI -->
        <div
            class="rounded-2xl bg-gray-100 p-6 grid gap-6 md:grid-cols-3 drop-shadow-xl"
        >
            <!--&nbsp; evita che “DemoBar”, “66” e “Bistrò” vengano spezzati su tre righe diverse quando lo schermo è molto stretto.-->
            <div>
            <h3 class="text-subt">DemoBar&nbsp;66&nbsp;Bistrò</h3>
            <p class="text-desc">Via&nbsp;Roma, 123 – Verona</p>
            <p class="text-desc">Tel: 045 1234567</p>
            </div>

            <div>
            <h3 class="text-subt">DemoBar&nbsp;66&nbsp;Beach</h3>
            <p class="text-desc">Lungomare, 456 – Rimini</p>
            <p class="text-desc">Tel: 0541 987654</p>
            </div>

            <div>
            <h3 class="text-subt">DemoBar&nbsp;66&nbsp;Bay</h3>
            <p class="text-desc">Piazza&nbsp;del&nbsp;Mare, 789 – Napoli</p>
            <p class="text-desc">Tel: 081 1234567</p>
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
    src: '/img/home/block/BlockBistroMob.png',
    alt: 'Bistrò',
    base: 'bg-[url(/img/home/block/Bistro.png)] bg-cover bg-center',
    hover: 'hover:bg-emerald-900',
    link: '/demo77-bistro'
  },
  {
    label: 'Beach',
    src: '/img/home/block/BlockBeachMob.png',
    alt: 'Beach',
    base: 'bg-[url(/img/home/block/Beach.png)] bg-cover bg-center',
    hover: 'hover:bg-fuchsia-900',
    link: '/demo77-beach'
  },
  {
    label: 'Bay',
    src: '/img/home/block/BlockBayMob.png',
    alt: 'Bay',
    base: 'bg-[url(/img/home/block/Bay.png)] bg-cover bg-center',
    hover: 'hover:bg-rose-950',
    link: '/demo77-bay'
  }
]
const partnerLogos = [
  '/img/partners/EthosPartner.png',
  '/img/partners/EthosPartner.png',
  '/img/partners/EthosPartner.png',
  '/img/partners/EthosPartner.png',
  '/img/partners/EthosPartner.png',
  '/img/partners/EthosPartner.png',
]
</script>

<style scoped>
/* padding-px / padding-py sono già definiti in main.css */
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
.ellipse {
  background-image: radial-gradient(ellipse at center, #00000059 30%, #0000 100%);
}
</style>