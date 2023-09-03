<style>
body {
    background-color:var(--galaxy-dark-blue);
}

button {
    background-color: var(--galaxy-dark-blue);
    border-radius: var(--default-border-radius);
    border-style: None;
    padding-top: 3px;
    padding-bottom: 3px;
    padding-left: 7px;
    padding-right: 7px;
    margin: 20px;
}
div.controler {
    display: flex;
    flex-direction: column;
    text-align: center;
    margin: 10px;
    padding: 10px;
}

img {
    height: 10vh;
}
</style>

<script>
const BASE_SERVER_ENDPOINT = "http://192.168.0.123:7878/";
async function handleResume() {
    let endpoint = BASE_SERVER_ENDPOINT + "resume";
    console.log(endpoint);
    let response = await fetch(endpoint);
}

async function handlePause() {
    let endpoint = BASE_SERVER_ENDPOINT + "pause";
    let response = await fetch(endpoint);
}

async function handleRewind() {
    let endpoint = BASE_SERVER_ENDPOINT + "rewind/10";
    let response = await fetch(endpoint);
}

async function handleAdvance() {
    let endpoint = BASE_SERVER_ENDPOINT + "advance/10";
    let response = await fetch(endpoint);
}

async function handleQuit() {
    let endpoint = BASE_SERVER_ENDPOINT + "quit";
    let response = await fetch(endpoint);
}
</script>

<body>
    <div class="controler">
        <button on:click={handleResume}>
            <img src="play.png" />
        </button>
        <button on:click={handlePause}>
            <img src="pause.png" />
        </button>
        <div>
            <button on:click={handleRewind}>
                <img src="rewind.png" />
            </button>
            <button on:click={handleAdvance}>
                <img src="advance.png" />
            </button>
        </div>
        <a href="/">
            <button on:click={handleQuit}>
                <img src="quit.png" />
            </button>
        </a>
    </div>
</body>
