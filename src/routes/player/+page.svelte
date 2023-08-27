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
    text-align: center;
    border: var(--galaxy-dark-blue) solid;
    border-radius: var(--default-border-radius);
    margin: 10px;
    padding: 10px;
}
</style>

<script>
async function handleResume() {
    let endpoint = `http://192.168.0.123:7878/resume`;
    let response = await fetch(endpoint);
}

async function handlePause() {
    let endpoint = `http://192.168.0.123:7878/pause`;
    let response = await fetch(endpoint);
}

async function handleRewind() {
    let endpoint = `http://192.168.0.123:7878/rewind/10`;
    let response = await fetch(endpoint);
}

async function handleAdvance() {
    let endpoint = `http://192.168.0.123:7878/advance/10`;
    let response = await fetch(endpoint);
}

async function handleQuit() {
    let endpoint = `http://192.168.0.123:7878/quit`;
    let response = await fetch(endpoint);
}
</script>

<div>
    <button on:click={handleResume}>Resume</button>
    <button on:click={handlePause}>Pause</button>
    <button on:click={handleRewind}>Rewind</button>
    <button on:click={handleAdvance}>Advance</button>
    <a href="/">
        <button on:click={handleQuit}>Quit</button>
    </a>
</div>
