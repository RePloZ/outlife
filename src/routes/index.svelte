<script lang="ts">
	import { HeaderPosition } from '$lib/type';
	import Header from '$lib/Header/index.svelte';
	import Home from '$lib/Home/index.svelte';
	import Moovies from '$lib/Moovies/index.svelte';
	import Informations from '$lib/Informations/index.svelte';
	import Booking from '$lib/Booking/index.svelte';
	import Contact from '$lib/Contact/index.svelte';
</script>

<svelte:head>
	<title>Outside Moovie</title>
</svelte:head>


<Header selectedPosition={HeaderPosition.Home} />
<main>
	<Home />
	<Moovies />
	<Informations />
	<Booking />
	<Contact />
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
