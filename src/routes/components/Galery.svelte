<style>
div.title {
    display: flex;    
}

h3 {
    display: flex;
    width: 150px;
    background-color: var(--galaxy-dark-blue);
    color: var(--galaxy-white);
    font-family: var(--default-font);
    border-top-left-radius: 15px;
    border-bottom-left-radius: 15px;
    border-top-right-radius: 45px;
    border-bottom-right-radius: 45px;
    text-align: center;
    padding-top: 2px;
    padding-bottom: 2px;
    padding-left:15px;
}

ul {
    list-style: none;
    background-color: var(--galaxy-dark-blue);
    border-radius: var(--default-border-radius);
    display: flex;
    flex-flow: row wrap;
}

li {
    width: 33%;
}
</style >

<script>
import { onMount } from "svelte";
import Movie from "./Movie.svelte";

let files = [];

onMount(async function () {
    let endpoint = "http://192.168.0.123:7878/";
    let response = await fetch(endpoint);
    files = await response.json();
});
</script>
<div clas="title">
    <h3>My galery</h3>
</div>
<div>
    <ul>
        {#each files as movie}
            <li>
                <Movie 
                       id={movie["id"]}
                       name={movie["name"]} 
                       duration={movie["duration"]}
                />
            </li>
        {/each}
    </ul>
</div>
