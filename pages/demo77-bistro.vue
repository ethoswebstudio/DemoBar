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
  bg-[url('/img/bistro/landingBistro.jpg')] bg-cover bg-center bg-no-repeat">
    <div class="text-shadow-lg/20 text-megat text-center  text-white">
        <p>DemoBar</p>
        <p>66</p>
        <p class="text-title">Bistrò</p>
    </div>
    </div>

    <!-- =============================================================== -->
    <!-- Menù-->
    <!-- =============================================================== -->

    <div 
    id="Menu"
    class="text-amber-50 bg-gray-700 flex-col padding-px padding-py relative items-center">
        <div class="relative flex-col justify-center">
            <h2 class="text-title">
            Cosa possiamo offrirti?
            </h2>
            <p class="text-desc pt-5">
            Scopri il nostro menù, una selezione di piatti preparati con ingredienti freschi e di alta qualità.
            Ogni piatto è una celebrazione dei sapori, pensato per soddisfare ogni palato.
            </p>
        </div>
            <div id="menuOption"
            class=" py-5 xl:py-10 text-amber-50">
            <div
                class="bg-emerald-800 text-title rounded-2xl py-3 xl:py-10 shadow-lg
                    transition transform duration-300 ease-out
                    hover:scale-105 hover:bg-emerald-900"
                >
                Menù
            </div>

            <div
                class="bg-fuchsia-800 text-title rounded-2xl py-3 xl:py-10 shadow-lg
                    transition transform duration-300 ease-out
                    hover:scale-105 hover:bg-fuchsia-900"
                >
                Drink
            </div>

            <div
                class="bg-rose-900 text-title rounded-2xl py-3 xl:py-10 shadow-lg col-span-2
                    transition transform duration-300 ease-out
                    hover:scale-105 hover:bg-rose-950"
             >
                Carta dei Vini
            </div>
        </div>
    </div>

    <!-- =============================================================== -->
    <!-- Chi Siamo  -->
    <!-- =============================================================== -->
    <div 
    id="Chisiamo"
    class="text-gray-700 flex flex-col lg:flex-row padding-px padding-py relative gap-12 bg-amber-50">
        <div class="relative flex-1 flex flex-col justify-center gap-4">
            <p class="text-title">Eleganza quotidiana.</p>
            <p class="text-desc">Benvenuto al DemoBar 66 Bistrò, dove il piacere del buon cibo incontra un’atmosfera intima e curata. Un luogo dove puoi fermarti per un caffè, un pranzo leggero o una cena gourmet in compagnia.</p>
            <h2 class="text-subt pt-3.5">Il nostro stile</h2>
            <p class="text-desc">
            <b>Ogni dettaglio è pensato per farti sentire speciale.</b>
            Dalla musica soffusa alle luci calde, ogni elemento del nostro bistrò è studiato per accoglierti in uno spazio raffinato ma accessibile. Il servizio è attento ma mai invadente, proprio come dev’essere.
            </p>
        </div>
        <div class="relative flex-1 max-w-md mx-auto lg:mx-0">
            <NuxtImg src="/img/carousel/BarImg.png" 
                 alt="img1"
                 class="shadow-xl/30 rounded-2xl"
            />
        </div> 
    </div>

    <!-- =============================================================== -->
    <!-- Bistrò --> 
    <!-- =============================================================== -->

    <div 
    id="Gallery"
    class="text-amber-50 bg-gray-700 flex flex-col lg:flex-row padding-px padding-py relative gap-12">
        <div class="relative flex-1 max-w-md mx-auto lg:mx-0">
            <Carousel />
        </div>
        <div class="relative flex-1 flex flex-col justify-center gap-4">
            <h2 class="text-title">
            Le nostre creazioni
            </h2>
            <p class="text-desc">
                Piatti che raccontano l’anima del nostro locale: eleganti ma accessibili, stagionali ma sorprendenti.
                Qui la cucina è un gesto d’amore, e ogni piatto è pensato per accoglierti, emozionarti e farti tornare.
            </p>
            <p class="text-subt">Un calice giusto per ogni piatto.</p>
            <p class="text-desc">La nostra selezione di vini spazia dai grandi classici alle etichette naturali. Ti aiutiamo a trovare l’abbinamento perfetto per valorizzare ogni portata.</p>
        </div>
    </div>
   


  </main>
</template>

<script setup>
definePageMeta({
  navItems: [
    { label: 'Menù',    href: '#Menu' },
    { label: 'Chi siamo', href: '#Chisiamo' },
    { label: 'Gallery', href: '#Gallery' },
    { label: 'Torna al gruppo', href: '/' }
  ]
})
</script>