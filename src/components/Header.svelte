<script lang="ts">
  import { goto } from '$app/navigation';
  import { page } from '$app/state';
  import { i18n } from '$lib/i18n';
  import { languageTag, type AvailableLanguageTag } from '$lib/paraglide/runtime';

  const { navigation }: { navigation: { name: string; href: string }[] } = $props();

  let isMobileMenuOpen = $state(false);
  const currentLanguage = languageTag();

  const languages: { name: string; code: AvailableLanguageTag }[] = [
    { name: 'Català', code: 'ca' },
    { name: 'Español', code: 'es' },
    { name: 'English', code: 'en' }
  ];

  function switchToLanguage(newLanguage: AvailableLanguageTag) {
    const canonicalPath = i18n.route(page.url.pathname);
    const localisedPath = i18n.resolveRoute(canonicalPath, newLanguage);
    goto(localisedPath);
  }
</script>

<header class="absolute inset-x-0 top-0 z-50">
  <nav class="flex items-center justify-between p-6 lg:px-8" aria-label="Global">
    <div class="flex lg:flex-1">
      <a href="/" class="-m-1.5 p-1.5">
        <span class="sr-only">Coral Jove del Conservatori de Sant Cugat</span>
        <img
          class="h-10 w-auto"
          src="/logo.png"
          alt="Logo Coral Jove del Conservatori de Sant Cugat"
        />
      </a>
    </div>
    <div class="flex lg:hidden">
      <button
        type="button"
        class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700"
        onclick={() => (isMobileMenuOpen = true)}
      >
        <span class="sr-only">Open main menu</span>
        <svg
          class="size-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          aria-hidden="true"
          data-slot="icon"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
          />
        </svg>
      </button>
    </div>
    <div class="hidden lg:flex lg:gap-x-12">
      {#each navigation as { name, href } (href)}
        <a {href} class="text-sm/6 font-semibold text-gray-900">{name}</a>
      {/each}
    </div>
    <div class="hidden gap-3 text-sm lg:flex lg:flex-1 lg:justify-end">
      {#each languages as { name, code } (code)}
        <button
          type="button"
          class="relative cursor-pointer before:absolute before:inset-x-0 before:-bottom-1 before:h-0.5 before:origin-left before:scale-x-0 before:bg-(--primary) before:transition-transform before:duration-500 hover:before:scale-x-100
          {currentLanguage === code ? 'font-semibold before:scale-x-100' : ''}"
          onclick={() => switchToLanguage(code)}
        >
          {name}
        </button>
      {/each}
    </div>
  </nav>

  <dialog
    class="lg:hidden"
    aria-modal="true"
    open={isMobileMenuOpen}
    onclose={() => (isMobileMenuOpen = false)}
  >
    <!-- Background backdrop, show/hide based on slide-over state. -->
    <div class="fixed inset-0 z-50"></div>
    <div
      class="fixed inset-y-0 right-0 z-50 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10"
    >
      <div class="flex items-center justify-between">
        <a href="/" class="-m-1.5 p-1.5">
          <span class="sr-only">Coral Jove del Conservatori de Sant Cugat</span>
          <img
            class="h-10 w-auto"
            src="/logo.png"
            alt="Logo Coral Jove del Conservatori de Sant Cugat"
          />
        </a>
        <button
          type="button"
          class="-m-2.5 rounded-md p-2.5 text-gray-700"
          onclick={() => (isMobileMenuOpen = false)}
        >
          <span class="sr-only">Tanca el menú</span>
          <svg
            class="size-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            aria-hidden="true"
            data-slot="icon"
          >
            <path stroke-linecap="round" stroke-linejoin="round" d="M6 18 18 6M6 6l12 12" />
          </svg>
        </button>
      </div>
      <div class="mt-6 flow-root">
        <div class="-my-6 divide-y divide-gray-500/10">
          <div class="space-y-2 py-6">
            {#each navigation as { name, href } (href)}
              <a
                {href}
                class="-mx-3 block rounded-lg px-3 py-2 text-base/7 font-semibold text-gray-900 hover:bg-gray-50"
                >{name}</a
              >
            {/each}
          </div>
          <div class="py-6">
            {#each languages as { name, code } (code)}
              <button
                class="-mx-3 block rounded-lg px-3 py-2.5 text-base/7 font-semibold text-gray-900 hover:bg-gray-50"
                onclick={() => switchToLanguage(code)}>{name}</button
              >
            {/each}
          </div>
        </div>
      </div>
    </div>
  </dialog>
</header>
