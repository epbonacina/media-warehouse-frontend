<style>
h3 {
    background-color: var(--galaxy-dark-blue);
    color:white;
    border-radius: var(--default-border-radius);
    text-align: center;
    padding-top: 2px;
    padding-bottom: 2px;
}

ul {
    list-style: none;
    background-color: pink;
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

<h3>My galery</h3>
<div>
    <ul>
        {#each files as movie}
            <li>
                <Movie 
                       id={movie["id"]}
                       name={movie["name"]} 
                       description={movie["description"]} 
                       duration={movie["duration"]}
                />
            </li>
        {/each}
    </ul>
</div>
