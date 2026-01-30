<script >
import { enhance } from "$app/forms";
import ElizaBot from 'elizabot';
const eliza = new ElizaBot();
let chat = $state([{ user: 'Eliza', message: eliza.getInitial() }]);

 async function write(message) {
    //Hämta HTML-elementet med id:et visible
    var element = document.getElementById("visible");
    //Ändrar elementets CSS-egenskap display till default
    element.style.display = "flex"; // Visa elementet
    
    //TODO: Add the new message to the chat
    chat.push({user:'me',message})
    // random delay for Eliza's response time
    await new Promise((r) => setTimeout(r, 1000 + Math.random() * 1000));
        element.style.display = "none"; // Visa elementet

    //TODO: Add Eliza's response to the chat
    chat.push({user:'Eliza',message:eliza.transform(message)})
  }
                
</script>
<main>
    <section>

        {#each chat as mess}
            <article class={mess.user}>
                <p>{mess.user}: {mess.message}</p>
            </article>
        {/each}
        <article id="visible">
            <span class=circle></span>
            <span class=circle></span>
            <span class=circle></span>
        </article>
    </section>
    <form method="post"
        
        use:enhance={({ formElement, formData, action, cancel }) => {
        cancel(); //don't post anything to server
        const text = formData.get("text"); // what does "text" refer to?
        write(text);
        formData.reset()
        }}>

            <input type="text" id="input" name="text">
       
    </form>
</main>
<style>
section{
    height: 100%;
    width: 100%;
    background-color: antiquewhite;
            overflow-y:scroll;
            display: flex;
            flex-direction: column;
}

article{
    padding: 5px;
    margin-bottom: 5px;
    width: 70%;
}

.Eliza{
    background-color:#478b56;
}
.me{
    background-color:#2f613a;
    text-align: right;
    align-self: flex-end;
    

}
    main{
        width:60vw;
        height:70vh;
        padding:10px;
        justify-items:center;
        background-color:lightblue;
        display: grid;
        grid-template-rows: 9fr 1fr;
        grid-template-columns: 1fr;
        margin:10px;
        padding:10px;
        border-radius:10px;
    }
#visible{
    width: 60px;
    height: 20px;
    display: none;
    background-color: black;
    justify-content: space-around;
    align-items: center;
    border-radius: 15px;
}
.circle{
    width:7px;
    height:7px;
    border-radius:50%;
    background-color:grey;        
    animation-name: typing;
    animation-duration: 1000ms; /* Längd på animationen (till exempel 3 sekunder) */
    animation-timing-function: ease-in-out; /* Funktion som styr tidsförloppet (till exempel "ease-in-out") */
    animation-iteration-count: infinite;
}
 
@keyframes typing {
    0% {transform: scale(1);}
    50% {transform: scale(1.4);}
    100% {transform: scale(1);}
}


    /* CSS-stilar för .circle med index 1 (den första cirkeln) */
    .circle:nth-child(1) {
        animation-delay: 0ms; /* Ingen fördröjning */
    }
    /* CSS-stilar för .circle med index 2 (den andra cirkeln) */
    .circle:nth-child(2) {
        animation-delay: 333ms; /* Starta animationen efter 333 millisekunder (ms) */
    }
    /* CSS-stilar för .circle med index 3 (den tredje cirkeln) */
    .circle:nth-child(3) {
        animation-delay: 666ms; /* Starta animationen efter 666 ms */
    }
    .eliza{
        
    }
</style>