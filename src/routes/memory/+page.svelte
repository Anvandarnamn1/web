<script>
    import { flip } from "svelte/animate";


    let cards = $state([])
    let imgs = [
        "park-trad.jpg",
        "/download (2).jpg",
        "/download (3).jpg",
        "/download (4).jpg",
        "/download (5).jpg",
        "/download (6).jpg",
    ]
    for (let i = 0; i < 12; i++) {
        cards.push({img: imgs[i%6], flipped: false,matched: false});
    }
    let bluepoint = $state(0);
    let redpoint = $state(0);
    let blueTurn = $state(true);
    function flipper(card){
        if (!card.flipped) {
                card.flipped = true
                let flippedCards = cards.filter(c=>c.flipped)
                flippedCards = flippedCards.filter(c=>c.matched==false)
                if (flippedCards.length >= 2){
                    if (flippedCards[0].img == flippedCards[1].img){
                        flippedCards[0].matched = true
                        flippedCards[1].matched = true
                        if (blueTurn == true){
                            bluepoint += 1
                        }
                        if (blueTurn == false){
                            redpoint += 1
                        }
                    }
                    else{
                        blueTurn = !blueTurn
                    }
                    setTimeout(() => {
                    cards.forEach((card) => {
                        card.flipped = card.matched;
                    });
                    flipcount = 0;
                    cards = cards;
                    }, 1000);    
                }   
        }
    }

</script>

<h1>Memory</h1> 
<main>
    {#each cards as card}
        <div class = "card" class:flipped={card.flipped}  onclick={()=>flipper(card)}>
            <img src={card.img} class="front">
            <img src="/download (7).jpg" class="back">
        </div>
 
    {/each}
</main>
             
<aside>
    <p>{redpoint}</p>
</aside>

<aside class = "blue">
    <p>{bluepoint}</p>
</aside>

<aside class = "turn" class:blue= { blueTurn }>
</aside>

<style>
    h1{
        justify-self: center;
    }

    .card img{
        position: absolute;
        width: 100%;
        height: 100%;
        backface-visibility: hidden;

    }

    main{
        display: grid;
        grid-template-columns: repeat(4,100px);
        grid-template-rows: repeat(3,100px); 
        justify-self: center;
    }
    .card{
        position: relative;
        border: 1px solid black;
        transform-style: preserve-3d;
        transition: all 0.5s;
        }
    aside{
        width: 100px;
        height: 100px;
        position: fixed;
        bottom: 10px;
        right: 10px;
        background-color: red;
        display: flex;
        justify-content: center;
        align-items: center;
        
    }

    p{
        font-size: 30px;
    }
    .blue{
        background-color: blue;
        left: 10px;
    }
    .turn{
        box-shadow: 0 0 10px 10px yellowgreen;
        z-index: -1;

    }
    .back{
        transform: rotateY(0deg);
    }
    .front, .flipped{
        transform: rotateY(180deg);
    }
</style>    