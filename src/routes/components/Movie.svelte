<style>
a {
    display: flex;
    justify-content: center;
}

div {
    border: var(--galaxy-white) solid;
    border-radius: var(--default-border-radius);
    border-width: 1px;
    margin: 10px;
}

.title {
    background-color: var(--galaxy-blue);
    font-family: var(--default-font);
    color: var(--galaxy-white);
    padding-top: 7px;
    padding-bottom: 7px;
    padding-left: 15px;
    padding-right: 15px;
}

div.metadata {
    display: flex;
    background-color: var(--galaxy-dark-blue);
    border-style: None;
    justify-content: space-around;
    align-items: center;
    height: 25px;
}

div.duration {
    display: flex;
    border-style: None;
    align-items: center;
}

p.duration {
    color: var(--galaxy-white);
    font-family: var(--default-font);
    text-align: center;
}

img.duration {
    margin-right: 15px;
    border-radius: var(--default-border-radius);
}

img {
    width: 25px;
    height: 25px;
}

button {
    background-color: var(--galaxylight-blue);
    border-style: None;
}

</style>

<script>
async function handleClick() {
    let endpoint = `http://192.168.0.123:7878/play/${id}`;
    let response = await fetch(endpoint);
}

export let id;
export let name;
export let duration;
</script>

<div>
    <p class="title">{name}</p>
    <div class="metadata">
        <a href="/player">
            <button on:click={handleClick}><img src="play.png" /></button>
        </a>
        <div class="duration">
            <img class="duration" src="clock.png" />
            <p class="duration">{duration}</p>
        </div>
    </div>
</div>
