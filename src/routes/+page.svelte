
<!--Delar upp sidan i två delar-->
<main>
  <div>

    <h1 class="name">Anton Westin </h1>
    <h2>Här har jag samlat min uppgifter jag gjort i samband med webbutveckling i årskurs 2 på Maja Beskowgymnasiet!</h2>
    <h3>Inspirerade citat för min webbutvecklingsresa:</h3>
    <!--Under denna kommer vi lägga till fler element-->
<p id="inspo">
        "The only way to learn a new programming language is by writing programs in it." - <strong>Dennis Ritchie</strong>, creator of the C programming language.
    </p>

    <p style="background-color:pink">
        "Every great developer you know got there by solving problems they were unqualified to solve until they actually did it." - <span>Patrick McKenzie, software engineer and entrepreneur</span>.
    </p>
    
  </div>
    <!--Här kommer vi lägga till en bild senare i uppgiften 1.2.4 Extra styling-->  

<svg viewBox="0 0 300 300" xmlns="http://www.w3.org/2000/svg">
<path fill="#FF0066" d="M29.5,-44C37.1,-41,41.4,-30.9,43.5,-21.3C45.7,-11.7,45.8,-2.5,46.6,8.2C47.5,19,49.1,31.5,43.9,38.7C38.7,45.9,26.6,47.8,14.3,53.8C1.9,59.9,-10.8,70,-18.4,66.2C-26,62.4,-28.6,44.7,-40.2,33.5C-51.8,22.4,-72.5,17.9,-75.7,9.6C-78.8,1.3,-64.3,-10.7,-56.1,-24.3C-47.8,-37.9,-45.8,-53,-37.5,-55.7C-29.2,-58.3,-14.6,-48.4,-1.8,-45.6C10.9,-42.7,21.9,-46.9,29.5,-44Z" transform=" translate(100,70)"  />
</svg>
</main>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="#0009ff" fill-opacity="1" d="M0,32L20,64C40,96,80,160,120,160C160,160,200,96,240,101.3C280,107,320,181,360,192C400,203,440,149,480,117.3C520,85,560,75,600,101.3C640,128,680,192,720,224C760,256,800,256,840,234.7C880,213,920,171,960,165.3C1000,160,1040,192,1080,197.3C1120,203,1160,181,1200,186.7C1240,192,1280,224,1320,202.7C1360,181,1400,107,1420,69.3L1440,32L1440,320L1420,320C1400,320,1360,320,1320,320C1280,320,1240,320,1200,320C1160,320,1120,320,1080,320C1040,320,1000,320,960,320C920,320,880,320,840,320C800,320,760,320,720,320C680,320,640,320,600,320C560,320,520,320,480,320C440,320,400,320,360,320C320,320,280,320,240,320C200,320,160,320,120,320C80,320,40,320,20,320L0,320Z"></path></svg>


<style>



h1, h2, h3, p {
        display: inline-block;
        /*Ger utrymme mellan element*/
        margin: 10px;
        }
  main{
    /*Styling för att dela upp sidan i två delar. */
    /*Vi kommer gå igenom detta i detalj senare*/
        
    /* Vi skiljer elementen med ett kommatecken(,) för att ge möjligheten till att ge flera element samma styling*/
   
            
    margin: auto;
    width: 80vw;
    height: 70vh;
    display: grid;
    grid-template-columns: repeat(2,50%);
    overflow: hidden;
  }
    h1{
        color:grey;
    }
    h2{
        color: rgb(255, 165, 0);
    }
    h3{
        color: #3cb371;
        font-family: sans-serif;
        font-weight: bold;
    }
    
    .name{
        font-family:'Gill Sans';
        font-size: 50px;
    }
    
    
    div{
        /*Styling för att centrera texten i behållaren*/
        margin: auto;
    }
    


    #inspo{
        font-family: courier;
        font-size: 160%;
    }

    span{
        color: green;
    }

  </style>