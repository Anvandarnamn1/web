<script>
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
	import { base } from '$app/paths';
</script>



<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<nav>
	<a href="{base}/">Hem</a>
<a href="{base}/photoapp">Photoapp</a>
</nav>

{@render children?.()}
