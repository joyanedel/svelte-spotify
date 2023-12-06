<script>
	import AsideMenu from '@components/AsideMenu.svelte';
</script>

<svelte:head>
	<title>Spotify</title>
	<meta name="description" content="Spotify" />
	<meta
		name="viewport"
		content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=0"
	/>
</svelte:head>

<div id="app" class="relative h-screen p-2 gap-2 bg-black">
	<aside class="[grid-area:aside] flex flex-col"><AsideMenu /></aside>
	<main class="[grid-area:main] bg-red-100 flex flex-col justify-center items-center">
		<div>
			<h1 class="text-4xl font-bold animated-colors">Como tan muchacho</h1>
			<h6 class="text-md font-bold text-right">Yo lo veo a ustede muy bien 2</h6>
		</div>
	</main>
	<footer class="[grid-area:player] bg-zinc-900 flex-1 min-h-[64px]">Player</footer>
</div>

<style>
	#app {
		display: grid;
		grid-template-areas: 'aside main main' 'player player player';
		grid-template-columns: 300px 1fr;
		grid-template-rows: 1fr auto;
	}

	.animated-colors {
		animation: colors 5s infinite;
	}

	@keyframes colors {
		0% {
			color: #ff0000;
		}
		25% {
			color: #00ff00;
		}
		50% {
			color: #0000ff;
		}
		75% {
			color: #ffff00;
		}
		100% {
			color: #ff00ff;
		}
	}
</style>
