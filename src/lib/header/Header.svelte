<script lang="ts">
	import { page } from '$app/stores';
	import logo from './tohru.png';
</script>

<header>
	<nav>
		<ul>
			<li class:active={$page.path === '/'}><a sveltekit:prefetch href="/"><img src={logo} alt="Tohru" /></a></li>
			<li class:active={$page.path === '/projects'}><a sveltekit:prefetch href="/projects">Projects</a></li>
		</ul>
	</nav>
</header>

<style>
	header {
        position:sticky;
        top: 0px;
        width: 100%;
		display: flex;
		justify-content: center;
        padding-top: 10px;
        background-image: linear-gradient(
            180deg,
            var(--secondary-color),
            transparent 
        );
	}

	nav {
		display: flex;
		justify-content: left;
        margin: 0px 15px 0px 15px;
        width: 90%;
        border-bottom: 3px solid var(--primary-color4);
	}

    nav img {
        width: 4em;
		height: 4em;
		object-fit: contain;
        border-radius: 50%;
    }

	ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 4em;
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
		background: var(--background);
		background-size: contain;
	}

	li {
		position: relative;
		height: 100%;
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 1em;
		color: var(--heading-color);
		font-weight: 700;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.1s linear;
	}

	a:hover {
		color: var(--accent-color);
	}
</style>
