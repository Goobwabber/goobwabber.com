<script lang="ts">
	import { page } from '$app/stores';
    import kofilogo from './kofi.png';
    import patreonlogo from './patreon.png';
</script>

<footer>
	<nav>
		<ul>
            <li><p>Please donate!</p></li>
            <li><a href="https://www.patreon.com/goobwabber"><img src={patreonlogo} alt="Patreon Logo" />Patreon</a></li>
            <li><a href="https://ko-fi.com/goobwabber"><img style="width:4em;height:4em;padding-right:5px;" src={kofilogo} alt="Ko-fi Logo" />Ko-fi</a></li>
		</ul>
	</nav>
</footer>

<style>
	footer {
        position: fixed;
        bottom: 0px;
        width: 100%;
		display: flex;
		justify-content: center;
        backdrop-filter: blur(var(--glass-blur));
        -webkit-backdrop-filter: blur(var(--glass-blur));
        background-image: linear-gradient(
            0deg,
            var(--primary-color),
            var(--primary-transparent)
        );
	}

	nav {
		display: flex;
		justify-content: left;
        margin: 0px 15px 0px 15px;
        width: 90%;
        border-top: 3px solid var(--primary-color4);
	}

    nav img {
        width: 2.5em;
		height: 2.5em;
		object-fit: contain;
        padding-right: 10px;
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

    nav p {
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
        margin: 0px;
    }

	a:hover {
		color: var(--accent-color);
	}
</style>