<script lang="ts">
  import * as m from '$lib/paraglide/messages.js';
  import AwardsTimeline from '../components/AwardsTimeline.svelte';
</script>

<div class="relative isolate px-6 lg:px-8">
  <div
    class="absolute inset-x-0 -top-40 -z-10 transform-gpu overflow-hidden blur-3xl sm:-top-80"
    aria-hidden="true"
  >
    <div
      class="relative left-[calc(50%-11rem)] aspect-[1155/678] w-[36.125rem] -translate-x-1/2 rotate-[30deg] bg-gradient-to-tr from-[var(--primary)] to-[#10a65a] opacity-30 sm:left-[calc(50%-30rem)] sm:w-[72.1875rem]"
      style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)"
    ></div>
  </div>
  <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-56">
    <div class="text-center">
      <h1 class="text-balance text-5xl font-semibold tracking-tight text-gray-900 sm:text-7xl">
        Coral Jove del Conservatori de Sant Cugat
      </h1>
      <p class="mt-8 text-pretty text-lg font-medium text-gray-500 sm:text-xl/8">
        Som un grup coral de joves d’entre 20 i 25 anys dirigits per Raimon Romaní
      </p>
      <div class="mt-10 flex items-center justify-center gap-x-6">
        <a href="#qui-som" class="text-sm/6 font-semibold text-gray-900"
          >{m.aboutUs()} <span aria-hidden="true">↓</span></a
        >
      </div>
    </div>
  </div>
  <div
    class="absolute inset-x-0 top-[calc(100%-13rem)] -z-10 transform-gpu overflow-hidden blur-3xl sm:top-[calc(100%-30rem)]"
    aria-hidden="true"
  >
    <div
      class="relative left-[calc(50%+3rem)] aspect-[1155/678] w-[36.125rem] -translate-x-1/2 bg-gradient-to-tr from-[var(--primary)] to-[#10a65a] opacity-30 sm:left-[calc(50%+36rem)] sm:w-[72.1875rem]"
      style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)"
    ></div>
  </div>
</div>

<div class="font-sans antialiased">
  <section id="director" class="bg-white py-20">
    <div class="mx-auto flex max-w-7xl flex-col items-center px-6 md:flex-row">
      <div class="mb-8 md:mb-0 md:w-1/2">
        <img
          src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhhQBzbiqgSlnmEVXVSSYam6b9QWTs6ss-RiRtJzG2TlTf9pOuUC1wUjNl5BkJLkmJJ_290eqWzUjxICcFHyU7dRM7LUgbDr94UZDDwtoDlLmOD-Ba3skJlSUFJ9isJPpy6NjBH/s2048/Foto+Raimon+Roman%25C3%25AD.tif"
          alt="Raimon Romaní"
          class="mx-auto rounded-lg"
          width="270"
          height="420"
        />
      </div>
      <div class="md:w-1/2 md:pl-12">
        <h2 class="mb-4 text-3xl font-bold">El nostre director</h2>
        <p class="mb-4 text-gray-700">
          Raimon Romaní és el cor i l'ànima de la Coral Jove. Amb una visió artística innovadora i
          un profund compromís amb la música, ha liderat el grup cap a nous horitzons, transformant
          cada actuació en una experiència única.
        </p>
        <p class="text-gray-700">
          La seva trajectòria i passió per l'art han inspirat generacions de joves, consolidant el
          nostre prestigi en concursos internacionals.
        </p>
      </div>
    </div>
  </section>

  <AwardsTimeline />

  <section id="contacte" class="bg-[var(--primary)] py-20 text-white">
    <div class="mx-auto max-w-7xl px-6">
      <h2 class="mb-12 text-center text-3xl font-bold">Contacte</h2>
      <div class="flex flex-col md:flex-row md:space-x-6">
        <div class="mb-6 flex-1 md:mb-0">
          <h4 class="text-xl font-semibold">Ubicació</h4>
          <p class="text-gray-200">Conservatori de Sant Cugat, Sant Cugat del Vallès.</p>
        </div>
        <div class="mb-6 flex-1 md:mb-0">
          <h4 class="text-xl font-semibold">Email</h4>
          <a href="mailto:coraljovestc@gmail.com" class="text-gray-200">coraljovestc@gmail.com</a>
        </div>
      </div>
    </div>
  </section>
</div>
