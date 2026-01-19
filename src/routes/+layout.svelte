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
<a href="{base}/photoapp">Fotoapp</a>
<a href="{base}/register">Register</a>
<a href="{base}/shoppinglist">Inköpslista</a>
<a href="{base}/memory">Memory</a>
<a href="{base}/test">test</a>
</nav>

{@render children?.()}
<style>
	
	:global(body), :global(html){
  		margin: 0%;
  		padding: 0%;
  		height: 100vh;
  		width: 100vw;
}    

</style>