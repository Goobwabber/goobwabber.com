<script>
    import { json } from "@sveltejs/kit";

    async function getRepos() {
        let response = await fetch("https://api.github.com/users/goobwabber/repos");
        let repos = await response.json();

        if (!response.ok)
            return null;
        
        repos.sort((a, b) => {
            // get how many years have passed from when it was last pushed to 2019, then multiply by value weight to push repos with recent activity to the top.
            var aActivity = (Date.parse(a.pushed_at) / 31536000000 - 49) * 20;
            var bActivity = (Date.parse(b.pushed_at) / 31536000000 - 49) * 20;
            var aVal = a.stargazers_count + a.watchers_count + a.forks + aActivity;
            var bVal = b.stargazers_count + b.watchers_count + b.forks + bActivity;
            return bVal - aVal;
        });

        return repos;
    }
    const promise = getRepos();
</script>

<svelte:head>
	<title>Projects</title>
</svelte:head>

<div class="content" style="margin-top:0px">
	<div class="flex">
        {#await promise}
            <p>Loading...</p>
        {:then repos}
        {#each repos as repo}
        {#if repo.fork == false && repo.name != "SoupBot" && repo.description != null}
            <div class="container">
                <div class="description">
                    <a href="{repo.html_url}"><h2><strong>{repo.name}</strong></h2></a>
                    <h3>{repo.description}</h3>
                </div>
                <div class="stats">
                    <svg class="inline" style="margin-left:0px;" height="17" width="17" viewBox="0 0 16 16">
                        <path fill-rule="evenodd" d="M8 .25a.75.75 0 01.673.418l1.882 3.815 4.21.612a.75.75 0 01.416 1.279l-3.046 2.97.719 4.192a.75.75 0 01-1.088.791L8 12.347l-3.766 1.98a.75.75 0 01-1.088-.79l.72-4.194L.818 6.374a.75.75 0 01.416-1.28l4.21-.611L7.327.668A.75.75 0 018 .25zm0 2.445L6.615 5.5a.75.75 0 01-.564.41l-3.097.45 2.24 2.184a.75.75 0 01.216.664l-.528 3.084 2.769-1.456a.75.75 0 01.698 0l2.77 1.456-.53-3.084a.75.75 0 01.216-.664l2.24-2.183-3.096-.45a.75.75 0 01-.564-.41L8 2.694v.001z"></path>
                    </svg>
                    <p class="inline"><strong>{repo.stargazers_count}  </strong></p>
                    <svg class="inline" height="17" width="17" viewBox="0 0 16 16">
                        <path fill-rule="evenodd" d="M5 3.25a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm0 2.122a2.25 2.25 0 10-1.5 0v.878A2.25 2.25 0 005.75 8.5h1.5v2.128a2.251 2.251 0 101.5 0V8.5h1.5a2.25 2.25 0 002.25-2.25v-.878a2.25 2.25 0 10-1.5 0v.878a.75.75 0 01-.75.75h-4.5A.75.75 0 015 6.25v-.878zm3.75 7.378a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm3-8.75a.75.75 0 100-1.5.75.75 0 000 1.5z"></path>
                    </svg>
                    <p class="inline"><strong>{repo.forks}</strong></p>
                    <!--<svg class="inline" width="17" height="17" viewBox="0 0 512 512"><path d="M448,224H380a128,128,0,0,0-247.9,0H64a32,32,0,0,0,0,64h68.05A128,128,0,0,0,380,288H448a32,32,0,0,0,0-64ZM256,320a64,64,0,1,1,64-64A64.07,64.07,0,0,1,256,320Z"/></svg>
                    <p class="inline"><strong>{repo.commit_count}</strong></p>-->
                    <p class="inline" style="float:right; margin:1px 18px 0px 0px; font-size:14px;">Updated: <strong>{repo.pushed_at.slice(0, 7)}</strong></p>
                </div>
            </div>
        {/if}
        {/each}
        {:catch error}
            <p style="color: red">{error.message}</p>
        {/await}
    </div>
</div>

<style>
    .container {
        flex-direction: column;
        justify-content: space-between;
        flex-grow: 1;
        padding: 0px;
    }

    .container .description {
        max-width: 300px;
        margin: 10px 10px 0px 20px;
    }

    .container .stats {
        padding: 10px 10px 10px 20px;
        border-top: 3px solid var(--dark-color);
        fill: var(--pure-white);
    }

    h2 {
        margin: 5px 0px 0px 0px;
    }

    .container a h2:hover {
        color: var(--accent-color);
    }

    h3 {
        font-size: 0.9rem;
    }

    .container a {
        font-size: 0.8rem;
        color: white;
    }

    .container a:hover {
        color: var(--accent-color);
    }

    .inline {
        vertical-align: middle;
        display: inline;
    }

    .stats svg {
        margin-left: 10px;
    }
</style>
