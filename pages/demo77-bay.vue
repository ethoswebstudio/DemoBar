<template>
  <main
  id="bistro"
  class="relative bg-white">
    <!-- =============================================================== -->
    <!-- LANDING / HERO                                                 -->
    <!-- =============================================================== -->
  <div 
  id="landing"
  class="relative isolate flex flex-col lg:flex-row justify-center padding-px padding-py">
    <div class="text-shadow-lg/20 text-megat text-center  text-gray-800">
        <p>DemoBar</p>
        <p>66</p>
    </div>
    </div>

    <!-- =============================================================== -->
    <!-- Menù-->
    <!-- =============================================================== -->

    <div 
    id="Menu"
    class="text-black bg-amber-50 flex-col padding-px padding-py relative items-center">
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
            class=" py-5 xl:py-10">
            <div
                class="bg-emerald-800 text-btn rounded-2xl py-3 xl:py-10 shadow-lg
                    transition transform duration-300 ease-out
                    hover:scale-105 hover:bg-emerald-900"
                >
                Menù
            </div>

            <div
                class="bg-fuchsia-800 text-btn rounded-2xl py-3 xl:py-10 shadow-lg
                    transition transform duration-300 ease-out
                    hover:scale-105 hover:bg-fuchsia-900"
                >
                Drink
            </div>

            <div
                class="bg-rose-900 text-btn rounded-2xl py-3 xl:py-10 shadow-lg col-span-2
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
    id="ChiSiamo"
    class="text-black flex flex-col lg:flex-row padding-px padding-py relative gap-12">
        <div class="relative flex-1 flex flex-col justify-center gap-4">
            <h2 class="text-title">
            Chi siamo
            </h2>
            <p class="text-desc">
            Boma77 nasce per regalare un’esperienza unica.
            Ogni dettaglio è curato con precisione per farti vivere momenti perfetti circondato dalle persone che preferisci.
            Cibo preparato con materie prime selezionate, carta vini studiata per esaltare anche i palati più esigenti e cocktail preparati da mani esperte con minuziosità.
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
    id="Bistro"
    class="text-black bg-amber-50 flex flex-col lg:flex-row padding-px padding-py relative gap-12">
        <div class="relative flex-1 flex flex-col justify-center gap-4">
            <h2 class="text-title">
            Il Bistrò
            </h2>
            <p class="text-desc">
            Piatti che trasmettono l'autenticità e la passione del nostro Bistrò. <br>
            Il cibo è il nostro amore e ogni giorno vogliamo accompagnarti in un viaggio culinario con un menù di stagione che varia utilizzando materie prime fresche e salutari.
            </p>
        </div>
        <div class="relative flex-1 max-w-md mx-auto lg:mx-0">
            <Carousel />
        </div>
    </div>
   


  </main>
</template>