<svelte:head>
	<title>Projects</title>
</svelte:head>

<div class="content">
	<h1>Projects</h1>

	<div class="flex">
        <div class="container">
            <div class="description">
                <h2><strong>MultiplayerExtensions</strong></h2>
                <h3>Core Beat Saber multiplayer mod.</h3>
            </div>
            <div class="links">
                <a href="https://github.com/Goobwabber/MultiplayerExtensions">Github</a>
            </div>
        </div>
        <div class="container">
            <div class="description">
                <h2><strong>BeatTogether</strong></h2>
                <h3>Modded matchmaking servers and game servers for Beat Saber multiplayer.</h3>
            </div>
            <div class="links">
                <a href="https://github.com/pythonology/BeatTogether.MasterServer">BeatTogether.MasterServer</a>
                <br><a href="https://github.com/pythonology/BeatTogether.DedicatedServer">BeatTogether.DedicatedServer</a>
            </div>
        </div>
        <div class="container">
            <div class="description">
                <h2><strong>BeatsaberOptimizer</strong></h2>
                <h3>Optimizes Beat Saber game code to perform better.</h3>
            </div>
            <div class="links">
                <a href="https://github.com/Goobwabber/BeatsaberOptimizer">Github</a>
            </div>
        </div>
        <div class="container">
            <div class="description">
                <h2><strong>PauseCoob</strong></h2>
                <h3>Allows you to pause Beat Saber by slicing a block rather than pressing a button.</h3>
            </div>
            <div class="links">
                <a href="https://github.com/Goobwabber/PauseCoob">Github</a>
            </div>
        </div>
        <div class="container">
            <div class="description">
                <h2><strong>MultiplayerAvatars</strong></h2>
                <h3>Shows other player's custom avatars in Beat Saber multiplayer</h3>
            </div>
            <div class="links">
                <a href="https://github.com/Goobwabber/MultiplayerAvatars">Github</a>
            </div>
        </div>
    </div>
</div>

<style>
	.content {
		width: 100%;
		max-width: 45em;
		margin: var(--column-margin-top) auto 0 auto;
	}

    .flex {
        flex-wrap: wrap;
        display: flex;
		justify-content: center;
    }

    .container {
        margin: 10px;
        border: 3px solid var(--primary-color5);
        border-radius: 5px;
        padding: 10px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        flex-grow: 1;
    }

    .container .description {
        max-width: 300px;
    }

    .container .links {
        padding-top: 5px;
        border-top: 3px solid var(--primary-color5);
    }

    h2 {
        margin: 5px 0px 0px 0px;
    }

    h3 {
        font-size: 0.9rem;
    }

    .container a {
        font-size: 0.8rem;
        color: white;
    }
</style>
