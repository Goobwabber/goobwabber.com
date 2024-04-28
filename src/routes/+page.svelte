<script context="module" lang="ts">
	export const prerender = true;
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<div class="content">
    <div class="flex">
        <div class="container" style="padding: 20px;">
            <h1 style="text-align:left; margin-top:10px; margin-bottom:10px;">
                Hi!
            </h1>
            <h2>
                I'm a full-stack developer that used to main work on Beat Saber mods.
		<br>I retired from Beat Saber modding somewhere in 2023. 
                <br>I prefer working with backend, but all development is fun!
            </h2>
        </div>
        <div class="container" style="">
            <a href="https://github.com/goobwabber">
                <svg xmlns="http://www.w3.org/2000/svg" width="150" height="150" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
            </a>
        </div>
        <div class="flex subflex">
            <div class="container smallcontainer">
                <a href="https://twitter.com/goobwabber">
                    <svg xmlns="http://www.w3.org/2000/svg" width="60" height="60" style="padding: 5px;" viewBox="0 0 24 24"><path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/></svg>
                </a>
            </div>
            <div class="container smallcontainer">
                <a href="https://www.patreon.com/goobwabber">
                    <svg xmlns="http://www.w3.org/2000/svg" width="50" height="50" style="padding: 10px;" viewBox="0 0 156.4 150.5"><circle cx="99.98" cy="56.41" r="56.41"/><rect width="27.57" height="150.5"/></svg>
                </a>
            </div>
            <div class="container smallcontainer">
                <a href="https://ko-fi.com/goobwabber">
                    <svg xmlns="http://www.w3.org/2000/svg" width="60" height="60" style="padding: 5px;" preserveAspectRatio="xMidYMid meet" viewBox="0 0 24 24"><path d="M23.881 8.948c-.773-4.085-4.859-4.593-4.859-4.593H.723c-.604 0-.679.798-.679.798s-.082 7.324-.022 11.822c.164 2.424 2.586 2.672 2.586 2.672s8.267-.023 11.966-.049c2.438-.426 2.683-2.566 2.658-3.734c4.352.24 7.422-2.831 6.649-6.916zm-11.062 3.511c-1.246 1.453-4.011 3.976-4.011 3.976s-.121.119-.31.023c-.076-.057-.108-.09-.108-.09c-.443-.441-3.368-3.049-4.034-3.954c-.709-.965-1.041-2.7-.091-3.71c.951-1.01 3.005-1.086 4.363.407c0 0 1.565-1.782 3.468-.963c1.904.82 1.832 3.011.723 4.311zm6.173.478c-.928.116-1.682.028-1.682.028V7.284h1.77s1.971.551 1.971 2.638c0 1.913-.985 2.667-2.059 3.015z"/></svg>
                </a>
            </div>
        </div>
    </div>
</div>

<style>
    a {
        display: flex;
    }

    a svg {
        fill: var(--pure-white);
    }

    a svg:hover {
        fill: var(--accent-color);
    }

    .container {
        flex-direction: column;
        justify-content: space-between;
        padding: 15px;
    }

    .smallcontainer {
        padding: 7.5px;
        margin: 5px;
    }

    .subflex {
        margin: 5px;
        align-items: flex-start;
        justify-content: start;
        flex: 1;
        min-height: 0;
        max-width: fit-content;
    }
</style>
