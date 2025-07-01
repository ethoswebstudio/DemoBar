<template>
  <main id="bay" class="relative bg-white">

    <!-- =============================================================== -->
    <!-- HERO / LANDING                                                  -->
    <!-- =============================================================== -->
    <section
      id="Landing"
      class="relative isolate flex flex-col lg:flex-row justify-center
             bg-[url('/img/bay/landingBay.jpg')] bg-cover bg-center bg-no-repeat
             text-white padding-px padding-landing"
    >
      <div class="text-center space-y-2">
        <p class="text-megat text-shadow-lg/20 leading-none">DemoBar</p>
        <p class="text-megat">66</p>
        <p class="text-title">Relax Bay</p>
      </div>
    </section>

    <!-- =============================================================== -->
    <!-- IL BAR                                                           -->
    <!-- =============================================================== -->
    <section
      id="IlBar"
      class="bg-blue-50 text-gray-700 flex flex-col lg:flex-row gap-12
             padding-px padding-py"
    >
      <div class="flex-1 flex flex-col justify-center gap-4">
        <h2 class="text-title">Non solo un drink, un rituale</h2>
        <p class="text-desc">
          Ogni cocktail nasce da una ricetta calibrata al millilitro, da
          ingredienti selezionati e da mani esperte.⠀Che tu preferisca i grandi
          classici o le creazioni originali del nostro mixologist, al Bay trovi
          sempre il bicchiere giusto per il tuo mood.
        </p>
      </div>

      <div class="flex-1 max-w-md mx-auto lg:mx-0">
        <NuxtImg
          src="/img/beach/drinkBeach.png"
          alt="Cocktail DemoBar 66 Bay"
          class="shadow-xl/30 rounded-2xl"
        />
      </div>
    </section>

    <!-- =============================================================== -->
    <!-- CICCHETTI & STUZZICHINI                                         -->
    <!-- =============================================================== -->
    <section
      id="Snack"
      class="bg-amber-50 text-gray-700 flex flex-col lg:flex-row-reverse gap-12
             padding-px padding-py"
    >
      <div class="flex-1 flex flex-col justify-center gap-4">
        <h2 class="text-title">Condividi, gusta, rilassati</h2>
        <p class="text-desc">
          Ogni drink è accompagnato da proposte sfiziose: taglieri di salumi
          gourmet, cicchetti creativi, mini-panini lievitati in casa, fritti
          croccanti ma leggeri. Ideali per un aperitivo lungo o una cena easy
          tra amici senza rinunciare alla qualità.
        </p>
      </div>

      <div class="flex-1 max-w-md mx-auto lg:mx-0">
        <NuxtImg
          src="/img/beach/mealBeach.png"
          alt="Stuzzichini DemoBar 66 Bay"
          class="shadow-xl/30 rounded-2xl"
        />
      </div>
    </section>

    <!-- =============================================================== -->
    <!-- GALLERY / CAROUSEL                                              -->
    <!-- =============================================================== -->
    <section
      id="Gallery"
      class="bg-blue-200 text-gray-700 flex flex-col lg:flex-row gap-12
             padding-px padding-py"
    >
      <div class="flex-1 max-w-md mx-auto lg:mx-0">
        <Carousel />
      </div>
      <div class="flex-1 flex flex-col justify-center gap-4">
        <h2 class="text-title">Drink vista tramonto</h2>
        <p class="text-desc">
          Spritz d’autore, bollicine italiane, signature cocktail speziati.
          Lasciati tentare dal nostro bartender e gusta il tuo drink
          preferito mentre il sole cala sull’orizzonte: semplicemente
          indimenticabile.
        </p>
      </div>
    </section>

    <!-- =============================================================== -->
    <!-- EVENTI & SERATE                                                 -->
    <!-- =============================================================== -->
    <section
      id="Eventi"
      class="bg-white text-gray-700 flex flex-col lg:flex-row-reverse gap-12
             padding-px padding-py"
    >
      <div class="flex-1 flex flex-col justify-center gap-4">
        <h2 class="text-title">C’è sempre un buon motivo per tornare</h2>
        <p class="text-desc">
          DJ-set nel weekend, quiz-night del mercoledì, karaoke del giovedì e
          feste private su richiesta. Al Bay succede sempre qualcosa: resta
          aggiornato sui nostri social e vivi ogni volta un’esperienza diversa.
        </p>
      </div>

      <div class="flex-1 max-w-md mx-auto lg:mx-0">
        <NuxtImg
          src="/img/beach/mealBeach.png"
          alt="Eventi DemoBar 66 Bay"
          class="shadow-xl/30 rounded-2xl"
        />
      </div>
    </section>

  </main>
</template>

<script setup>
definePageMeta({
  navItems: [
    { label: 'Il bar',            href: '#IlBar'   },
    { label: 'Snack',             href: '#Snack'   },
    { label: 'Gallery',           href: '#Gallery' },
    { label: 'Eventi',            href: '#Eventi'  },
    { label: 'Torna al gruppo',   href: '/'        }
  ]
})
</script>