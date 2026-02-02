<script>
  // Importera goto-funktionen för att navigera mellan sidor
  import { goto } from '$app/navigation';
  
  // Funktion som hanterar formulärets submit-händelse
  function handleSubmit(e) {
    // Förhindra att sidan laddas om (standardbeteende för formulär)
    e.preventDefault();
    
    // Skapa ett FormData-objekt från formuläret
    const formData = new FormData(e.target);
    
    // Hämta värdet från input-fältet med name="search"
    const search = formData.get('search');
    
    // Navigera till den dynamiska routen /search/[pokemon]
    goto('/search/' + search);
  }
</script>
<main> 
    <form onsubmit={handleSubmit}>
        <input type="text" name="search" placeholder="Sök upp en pokemon" />
    </form>
                 
    <slot>

    </slot>
</main>
<div class="backdrop">
</div>
<style>
    main{
        display:flex;
        width:100vw;
        height:80vh;
        background-color:rgba(255, 255, 255, 0.8);
        margin: 5vh auto;
        border:3px;
        border-radius:10px;
        flex-direction:column;
        align-items:center;
        justify-items:center;
    }
    .backdrop{
        width:100vw;
        height:100vh;
        background-image: url('https://imageio.forbes.com/specials-images/imageserve/604202ff091b6539cb90fcbc/The-backs-of-a-number-of-Pok-mon-cards-/960x0.jpg?format=jpg&width=960' );
        background-size: cover;
        position: fixed;
        top:0;
        left:0;
        z-index: -1;
        filter: blur(3px);
    }
</style>