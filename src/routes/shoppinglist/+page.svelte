
<script>
    import { fade } from 'svelte/transition';
    let varor = $state([{ name:"Mjölk" , köpt:false}]);
    let new_vara = $state("");
    function nya_varor(e){
        e.preventDefault();
        varor.push({name: new_vara,köpt:false});
       
        
    }
</script>
<main class = container>
    <h1> Shoppinglist</h1>
    <div class = "categories_container">
        
        <section>
            <h2>Varor att köpa</h2> 
                <ol>
                    
                    {#each varor as vara, i}
                    {#if !vara.köpt}
                        <li transition:fade>
                            {vara.name} <button onclick={()=>{varor.splice(i,1)}}>X</button> <button onclick={()=>{vara.köpt =true}}>Köpt</button>
                            <hr>
                        </li>
                        {/if}
                    {/each}
                </ol>
           
        </section>
        
        <section>
            <h2>Köpta varor</h2>
                <ul>
                    {#each varor as vara, i}
                        {#if vara.köpt}
                            <li>
                                {vara.name} <button onclick={()=>{varor.splice(i,1)}}>X</button>
                            </li>
                            {/if}
                    {/each}
                </ul>
        </section>
        
    </div>
            
                <form onsubmit={nya_varor}> 
                    <label for="text">Lägg till vara:</label>
                    <input type="text" id="text" bind:value={new_vara} >
                    {#if new_vara.trim().length > 0}
                        
                        <input type="submit" value="Lägg till">
                        {:else}
                            <p style="color:red;">Varans namn får inte vara tomt</p>
                            {/if}
                    
                    
                </form>
</main>
        
    <style>


        h2{
            margin:0;
            padding: 5px 0;
            text-align: center;
            background-color: rgba(255, 255, 255, 0.3);
        }
        .container{
            margin: 30px auto;
            background-color: lightblue;
            width: 90vw;
            height: 90vh;
            border-radius: 20px;
            height: 100%;
            display: grid;
            grid-template-rows: 1fr 9fr 1fr;
        }
        .container h1{
            background-color: green;
            margin: 20px;
            justify-self: center;
            align-items: center; 
        }
        .categories_container{
            background-color: lightblue;
            display: grid;
            grid-template-columns: repeat(2,1fr);
            grid-gap:10px;
            width: 100%;
            height: 100%;    
            list-style-type:square
        }
        ul{
            list-style-type:square;
        }
        ol{
            list-style-type:upper-roman;
        }
        
        .categories_container section:nth-child(odd)  {  /* vilket barn vill vi styla? */
            background-color: rgba(0, 0, 0, 0.1) /* svart bakgrund med 10% opacitet */
        }
        
        .categories_container section:nth-child(even)  {  /* vilket barn vill vi styla? */
            background-color: rgba(0, 0, 0, 0.3) /* svart bakgrund med 30% opacitet */
        }

    </style>
