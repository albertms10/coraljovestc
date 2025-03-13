<script lang="ts">
  import { i18n } from '$lib/i18n';
  import { ParaglideJS } from '@inlang/paraglide-sveltekit';
  import '../app.css';
  import Footer from '../components/Footer.svelte';
  import Header from '../components/Header.svelte';

  let { children } = $props();

  const navigation = [
    { name: 'Qui som', href: '#qui-som' },
    { name: 'Trajectòria', href: '#trajectoria' },
    { name: 'Concerts', href: '#concerts' },
    { name: 'Contacte', href: '#contacte' }
  ];
</script>

<ParaglideJS {i18n}>
  <div class="flex h-dvh flex-col">
    <Header {navigation} />
    <main class="flex-grow">{@render children()}</main>
    <Footer {navigation} />
  </div>
</ParaglideJS>
