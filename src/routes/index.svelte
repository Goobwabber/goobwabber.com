<script context="module" lang="ts">
	export const prerender = true;
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<h1>
		<div class="welcome">
			Hi!
		</div>
	</h1>

	<h2 style="text-align: center;">
		I'm a Full-stack developer that mainly works on Beat Saber mods.
        <br> I prefer working with backend, but all development is exciting.
        <br> Check out my <strong><a href="https://github.com/goobwabber">Github</a></strong> to see some cool stuff I've made!
	</h2>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(15%) 0;
	}
</style>
