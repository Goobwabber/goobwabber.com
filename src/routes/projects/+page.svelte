<script>
    async function getRepos() {
        let response = await fetch("https://api.github.com/users/goobwabber/repos");
        let repos = await response.json();

        if (!response.ok)
            return null;

        for (let i = 0; i < repos.length; i++) {
            let releaseResponse = await fetch(repos[i].releases_url);
            let releases = await releaseResponse.json(); 

            let downloads = 0;
            for (let x = 0; x < releases.length; x++) {
                for (let y = 0; y < releases[x].assets.length; y++) {
                    downloads += releases[x].assets[y].download_count;
                }
            }
            repos[i].downloads = downloads;
        }
        
        repos.sort((a, b) => {
            var aVal = a.stargazers_count + a.watchers_count + a.forks + a.downloads;
            var bVal = b.stargazers_count + b.watchers_count + b.forks + b.downloads;
            return bVal - aVal;
        });
        return repos;
    }
    const promise = getRepos();
</script>

<svelte:head>
	<title>Projects</title>
</svelte:head>

<div class="content">
	<div class="flex">
        {#await promise}
            <p>Loading...</p>
        {:then repos}
        {#each repos as repo}
        {#if repo.fork == false}
            <div class="container">
                <div class="description">
                    <a href="{repo.html_url}"><h2><strong>{repo.name}</strong></h2></a>
                    {#if repo.description != null}
                    <h3>{repo.description}</h3>
                    {/if}
                </div>
                <div class="links">
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
</style>
