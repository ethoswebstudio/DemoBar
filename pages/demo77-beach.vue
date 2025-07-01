<template>
  <main
  id="bistro"
  class="relative bg-white">
    <!-- =============================================================== -->
    <!-- LANDING / HERO                                                 -->
    <!-- =============================================================== -->
  <div 
  id="landing"
  class="relative isolate flex flex-col lg:flex-row justify-center padding-px padding-landing
  bg-[url('/img/beach/landingBeach.png')] bg-cover bg-center bg-no-repeat">
    <div class="text-shadow-lg/20 text-megat text-center  text-white">
        <p>DemoBar</p>
        <p>66</p>
        <p class="text-title">Beach club</p>
    </div>
    </div>

    <!-- =============================================================== -->
    <!-- Menù-->
    <!-- =============================================================== -->

    <div 
    id="Menu"
    class="text-gray-700 bg-blue-200 flex-col padding-px padding-py relative items-center">
        <div class="relative flex-col justify-center">
            <h2 class="text-title text-shadow-lg">
            Pesce fresco, sapori veri.
            </h2>
            <p class="text-desc pt-5">
            Ogni piatto è preparato con ingredienti locali e stagionali. Dalle tartare ai primi piatti classici, fino alla nostra frittura mista, la cucina del Beach celebra il mare in ogni forma.
            </p>
        </div>
            <div id="menuOption"
            class=" py-5 xl:py-10 text-amber-50">
            <div
                class="bg-yellow-500 text-title rounded-2xl py-3 xl:py-10 shadow-lg col-span-2 xl:col-span-1
                    transition transform duration-300 ease-out
                    hover:scale-105 hover:bg-yellow-600"
                >
                Menù
            </div>

            <div
                class="bg-rose-700 text-title rounded-2xl py-3 xl:py-10 shadow-lg col-span-2 xl:col-span-1
                    transition transform duration-300 ease-out
                    hover:scale-105 hover:bg-rose-950"
             >
                Carta dei Vini
            </div>
        </div>
    </div>

    <!-- =============================================================== -->
    <!-- il locale  -->
    <!-- =============================================================== -->
    <div 
    id="locale"
    class="text-gray-700 flex flex-col lg:flex-row padding-px padding-py relative gap-12 bg-amber-50">
        <div class="relative flex-1 flex flex-col justify-center gap-4">
            <h2 class="text-title">
            Ristorante fronte mare, anima mediterranea.
            </h2>
            <p class="text-desc">
            Al DemoBar 66 Beach puoi vivere il mare con tutti i sensi: gustare piatti di pesce freschissimo, rilassarti in riva al mare e brindare con un aperitivo al tramonto.
            Siamo aperti tutto il giorno, dal pranzo alla cena. Ti accogliamo in un ambiente luminoso, informale e rilassante, perfetto per staccare la spina e goderti il panorama.
            </p>
        </div>
        <div class="relative flex-1 max-w-md mx-auto lg:mx-0">
            <NuxtImg src="/img/beach/MealBeach.png" 
                 alt="img1"
                 class="shadow-xl/30 rounded-2xl"
            />
        </div> 
    </div>

    <!-- =============================================================== -->
    <!-- Gallery --> 
    <!-- =============================================================== -->

    <div 
    id="Gallery"
    class="text-gray-700 bg-blue-200 flex flex-col lg:flex-row padding-px padding-py relative gap-12">
        <div class="relative flex-1 max-w-md mx-auto lg:mx-0">
            <Carousel />
        </div>
        <div class="relative flex-1 flex flex-col justify-center gap-4">
            <h2 class="text-title">
            Drink vista mare.
            </h2>
            <p class="text-desc">
            Cocktail freschi, bollicine italiane e piccoli assaggi da condividere. Il momento dell’aperitivo al Beach è qualcosa da provare… e rifare.
            Il nostro barista ti aspetta con una selezione di drink classici e speciali, preparati con ingredienti freschi e di qualità. Scegli il tuo preferito e goditi il tramonto in riva al mare.
            </p>
        </div>
    </div>
   


  </main>
</template>

<script setup>
definePageMeta({
  navItems: [
    { label: 'Menù',    href: '#Menu' },
    { label: 'Il locale', href: '#locale' },
    { label: 'Gallery', href: '#Gallery' },
    { label: 'Torna al gruppo', href: '/' }
  ]
})
</script>