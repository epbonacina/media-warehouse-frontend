<style>
button {
    background-color: var(--galaxy-dark-blue);
    color: white;
    border-radius: var(--default-border-radius);
    border-style: None;
    padding-top: 3px;
    padding-bottom: 3px;
    padding-left: 7px;
    padding-right: 7px;
    text-align: center;
}

div {
    border: black solid;
    border-radius: var(--default-border-radius);
    margin: 10px;
    padding: 10px;
}

.title {
    border-radius: var(--default-border-radius); 
    background-color: var(--galaxy-dark-blue);
    color: white;
    padding-top: 7px;
    padding-bottom: 7px;
    padding-left: 15px;
    padding-right: 15px;
}
</style>

<script>
function handleClick() {
    console.log("This button is working");
}
</script>

<div>
    <p class="title">A very, very large title, that should not fit in a single movie</p>
    <p>A very, very large author name, that should not fit in a single movie</p>
    <p>Duration 1</p>
    <p>Image 1</p>
    <button on:click={handleClick}>Play</button>
</div>
