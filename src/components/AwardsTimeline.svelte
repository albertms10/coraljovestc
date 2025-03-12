<script lang="ts">
  import Card from './Card.svelte';
  import Medal from './Medal.svelte';

  function getMedalColor(title: string) {
    if (title.toLowerCase().includes('fundació')) return 'bg-blue-500';
    if (title.startsWith('1r')) return 'bg-yellow-500';
    if (title.startsWith('2n')) return 'bg-gray-400';
    if (title.startsWith('3r')) return 'bg-orange-600';
    return 'bg-indigo-600';
  }

  function getMedalText(title: string) {
    if (title.toLowerCase().includes('fundació')) return 'Fnd';
    if (title.startsWith('1r')) return '1r';
    if (title.startsWith('2n')) return '2n';
    if (title.startsWith('3r')) return '3r';
    return '';
  }

  // Dades de la línia del temps
  let timelineAwards = [
    {
      year: '2019',
      title: 'Fundació',
      description: 'La fundació de la Coral Jove, iniciant una nova era musical.',
      image: '/images/fundacio.jpg'
    },
    {
      year: '2019',
      title: '1r Premi Avilés',
      description: 'Reconegut al concurs d’Avilés per la seva excel·lència.',
      image: '/images/aviles.jpg'
    },
    {
      year: '2023',
      title: '1r Premi Binissalem',
      description: 'Premi a Binissalem, destacant el nostre compromís artístic.',
      image: '/images/binissalem.jpg'
    },
    {
      year: '2024',
      title: '3r Premi Cocentaina',
      description: 'Un tercer premi a Cocentaina que celebra la nostra creativitat.',
      image: '/images/cocentaina.jpg'
    },
    {
      year: '2024',
      title: '2n Premi Vitoria',
      description: 'Segon premi a Vitoria per una actuació inspiradora.',
      image: '/images/vitoria.jpg'
    },
    {
      year: '2025',
      title: '1r Premi Ciudad de Granada',
      description: 'El primer premi a la ciutat de Granada, reafirmant la nostra qualitat.',
      image: '/images/granada.jpg'
    }
  ];
</script>

<section id="awards" class="relative bg-gray-100 py-20">
  <div class="relative mx-auto max-w-7xl px-6">
    <h2 class="mb-12 text-center text-3xl font-bold text-indigo-600">Els nostres Premis</h2>

    <div
      class="absolute left-1/2 top-0 hidden h-full w-1 -translate-x-1/2 transform bg-slate-300 md:block"
    ></div>

    <div class="space-y-12">
      {#each timelineAwards as item, index}
        <div class="relative">
          <div class="hidden md:grid md:grid-cols-3 md:items-center">
            {#if index % 2 !== 0}
              <div class="md:col-start-1 md:pr-8">
                <Card {item} />
              </div>
            {/if}
            <Medal label={getMedalText(item.title)} color={getMedalColor(item.title)} />
            {#if index % 2 === 0}
              <div class="md:col-start-3 md:pl-8">
                <Card {item} />
              </div>
            {/if}
          </div>

          <div class="flex flex-col items-center md:hidden">
            <div
              class="flex h-12 w-12 items-center justify-center rounded-full font-bold text-white {getMedalColor(
                item.title
              )}"
            >
              {getMedalText(item.title)}
            </div>
            <div class="mt-4 w-full">
              <Card {item} />
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>
