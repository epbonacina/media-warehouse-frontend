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

.description {
    border-top: 3px solid var(--galaxy-white);
    border-radius: var(--default-border-radius);
    border-bottom: 3px solid var(--galaxy-white);
    font-family: var(--default-font);
    color: var(--galaxy-white);
    background-color: var(--galaxy-purple);
    padding:5px;
}
</style>

<script>
async function handleClick() {
    let endpoint = `http://192.168.0.123:7878/play/${id}`;
    let response = await fetch(endpoint);
}

export let id;
export let name;
export let description;
export let duration;
</script>

<div>
    <p class="title">{name}</p>
    <p class="description">{description}</p>
    <p class="duration">{duration}</p>
    <p>Image 1</p>
    <a href="/player">
        <button on:click={handleClick}>Play</button>
    </a>
</div>
