<script>
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
	import { base } from '$app/paths';
</script>



<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<nav class="nav">
<a href="{base}/"class="link">Hem</a>
<a href="{base}/photoapp"class="link">Fotoapp</a>
<a href="{base}/register"class="link">Register</a>
<a href="{base}/shoppinglist"class="link">Inköpslista</a>
<a href="{base}/memory"class="link">Memory</a>
<a href="{base}/chat"class="link">Chat</a>
<a href="{base}/search"class="link">Search</a>
<a href="{base}/test"class="link">test</a>
</nav>

{@render children?.()}
<style>
	
	:global(body), :global(html){
  		margin: 0%;
  		padding: 0%;
  		height: 100vh;
  		width: 100vw;
		
}    
.nav{
	background-color:lightblue;
	padding:3px;

}
.link{
	color:black;
}
</style>