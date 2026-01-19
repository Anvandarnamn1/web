<script>
    let color = "black";
    let name = "";
    let colors = [{namn: "Blå", value: "blue"}, {namn: "Röd", value: "red"}];
    function handleSubmit(){
        alert ("Välkommen "+ name +'!')
    }
    
    import {users_store} from "$lib/user";
    let users = [];
    
    import { onMount } from 'svelte';
    onMount(() => {
        /*Check if has more then 2 characters*/
        if($users_store.length > 2){
            users = JSON.parse($users_store);
            console.log(users);
        }
    });
    


   
    function registrering(){
        alert (name + " finns redan! Du kan inte registrera dig med det namnet.")
    if (users.find(person => person.name === name) != null) {
            console.log("Found Anton");
        }
        else {
            let new_user = {username: name, password: password, email: email, color: color};
    users = [...users, new_user];
    $users_store = JSON.stringify(users);
        }

    }
    

    
</script>
<main>
    
<div class= "flex-container">
    <h1> Register </h1>
    
    
    <form on:submit|preventDefault={registrering}> 
        <div style="width: 100px; height: 100px; border-radius: 50%; overflow:hidden; background-color:{color};"></div>
        <label for="name">Namn:</label>
        <input type="text" id="name" bind:value={name} >
        <label for="text">Epostadress:</label>
        <input type="text" id="text" >
        <label for="favoritfärg">Favoritfärg:</label>
        <select id="favoritfärg" bind:value={color}>
        {#each colors as c}
            <option value={c.value}>{c.namn}</option>
        {/each}
        </select>
        <label for="text">Lösenord:</label>
        <input type="text" id="blue" >
        <input type="submit" value="Registrera">
        Har du redan ett konto<a href="/login">Logga in!</a>
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
        height: 80%;
        background-color: #3a2e3b;
        margin: auto;
        flex-direction:column;
        justify-content:center;
        justify-content:space-evenly;
        min-width: 300px;
        min-height: 500px;
        
    }     
 
</style>
