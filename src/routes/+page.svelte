<script lang="ts">
	import { goto } from '$app/navigation';
	import { page } from '$app/state';
	import { i18n } from '$lib/i18n';
	import * as m from '$lib/paraglide/messages.js';
	import type { AvailableLanguageTag } from '$lib/paraglide/runtime';

	function switchToLanguage(newLanguage: AvailableLanguageTag) {
		const canonicalPath = i18n.route(page.url.pathname);
		const localisedPath = i18n.resolveRoute(canonicalPath, newLanguage);
		goto(localisedPath);
	}
</script>

<h1>Coral Jove del Conservatori de Sant Cugat</h1>
<h2>{m.welcome()}</h2>
<footer>
	<button onclick={() => switchToLanguage('en')}>English</button>
	<button onclick={() => switchToLanguage('es')}>Español</button>
	<button onclick={() => switchToLanguage('ca')}>Català</button>
</footer>
