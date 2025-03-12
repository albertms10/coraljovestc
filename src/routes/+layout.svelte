<script lang="ts">
  import { i18n } from '$lib/i18n';
  import { ParaglideJS } from '@inlang/paraglide-sveltekit';
  import '../app.css';
  import Footer from '../components/Footer.svelte';
  import Header from '../components/Header.svelte';

  let { children } = $props();
</script>

<ParaglideJS {i18n}>
  <Header />
  {@render children()}
  <Footer />
</ParaglideJS>
