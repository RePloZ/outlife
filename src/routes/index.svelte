<script lang="ts">
	import Header from '$lib/Header/index.svelte';
	import { HeaderPosition } from '$lib/Header/type';
	import Home from '$lib/Home/index.svelte';
	import Moovies from '$lib/Moovies/index.svelte';
	import Informations from '$lib/Informations/index.svelte';
</script>

<svelte:head>
	<title>Outside Moovie</title>
</svelte:head>


<Header selectedPosition={HeaderPosition.Home} />
<main>
	<Home />
	<Moovies />
	<Informations />
</main>

<style>
	main {
		width: 100%;
		height: 100%;
		overflow: hidden;
		top: 54px;
	}

	body {
		padding: 0;
		margin: 0;
	}

</style>
