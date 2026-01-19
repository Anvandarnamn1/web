<main>
    <h1>Färger</h1>
    <h6>Syntest</h6>

    <div class = "box">
        
        <div class = colorbox1>
            <h2>1</h2>
        </div>
        <div class = colorbox2>
            <h2>2</h2>
        </div>
        <div class = colorbox3>
            <h2>3</h2>
        </div>
        <div class = colorbox4>
            <h2>4</h2>
        </div>
        <div class = colorbox5>
            <h2>5</h2>
        </div>
        <div class = colorbox6>
            <h2>6</h2>
        </div>
    </div>

</main>
<style>
    .box{
        display: flex;
        background-color: lightgrey;
        max-width: 50vw;
        flex:0;
        border: solid 2px black;
        flex-wrap: wrap;
    }
    .colorbox1{
        display:flex;
        background-color:red;
        justify-content: center;
        align-items: center;
        min-width: 15vw;
    }
    .colorbox2{
        display:flex;
        background-color:blue;
        justify-content: center;
        align-items: center;
        min-width: 15vw;
    }
    .colorbox3{
        display:flex;
        background-color:green;
        justify-content: center;
        align-items: center;
        min-width: 15vw;
    }
    .colorbox4{
        display:flex;
        background-color:yellow;
        justify-content: center;
        align-items: center;
        min-width: 15vw;
    }
    .colorbox5{
        display:flex;
        background-color:purple;
        justify-content: center;
        align-items: center;
        min-width: 15vw;
    }
    .colorbox6{
        display:flex;
        background-color:orange;
        justify-content: center;
        align-items: center;
        min-width: 15vw;
    }
    </style>