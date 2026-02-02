<script>
  /** @type {import('./$types').PageData} */
  export let data;
</script>

{#await data}
  <p>.. waiting</p>
{:then pokemon} 
<article>
  {#each Object.entries(pokemon.response.sprites) as sprites}
    {#if typeof sprites[1] == "string"}
    <img src={sprites[1]} />
    {/if}
  {/each}
</article>
<h1>{pokemon.response.name}</h1>
<section>
<h2>Weight: {pokemon.response.weight}</h2>
<h2>Order: {pokemon.response.order}</h2>
<h2>Height: {pokemon.response.height}</h2>
</section>

{/await}  
<style>
    article{
        display:flex;
        width:90vw;
        height:30vh;
        gap:1em;
    }
</style>