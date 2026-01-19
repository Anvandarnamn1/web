<script>
    let color = "black";
    let name = "";
    let colors = [{namn: "Blå", value: "blue"}, {namn: "Röd", value: "red"}];
    function handleSubmit(){
        alert ("Välkommen "+ name +'!')
    }
    
</script>
<main>
    
<div class= "flex-container">
    <h1> Inloggning </h1>
    
    
    <form on:submit|preventDefault={handleSubmit}> 
        <label for="text">Epostadress:</label>
        <input type="text" id="text" bind:value={name}>
        <label for="text">Lösenord:</label>
        <input type="text" id="text" >
        <input type="submit" value="Logga in">
    </form>
</div>
</main>

<style>


form{
    display: flex;
    flex-direction: column;
    color: gray;
    font-size: 20px;
    gap: 10px;
    align-items: center;}
    
 main{
        background-image: url("https://t4.ftcdn.net/jpg/05/21/65/59/360_F_521655929_N80d5GaCQJ2VP073PfTXJTe9mkvsNtHE.jpg");
        background-size: cover;
        width: 100%;
        height: 100%;
        padding: 5%;
        min-width: 500px;
        min-height: 500px;
    }
    
    .flex-container{
        display: flex;
        border: solid 5px rosybrown;
        border-radius: 10px;
        width: 35%;
        height: 40%;
        background-color: #3a2e3b;
        margin: auto;
        flex-direction:column;
        justify-content:center;
        justify-content:space-evenly;
        min-width: 100px;
        min-height: 200px;
    }     
        
</style>
