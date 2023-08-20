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
import Movie from "./Movie.svelte";

function getVideoFiles() {
    console.log("Getting all available movies");
    return ["banana", "maçã", "melancia", "laranja", "melão"];
}

let files = getVideoFiles();
</script>

<h3>My galery</h3>
<div>
    <ul>
        {#each files as file}
            <li><Movie /></li>
        {/each}
    </ul>
</div>
