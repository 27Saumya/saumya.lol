<script lang="ts">
	import '../app.css';
	import Header from '../components/Header.svelte';
	import Footer from '../components/Footer.svelte';

	let innerHeight = 0;
	let innerWidth = 0;
</script>

<div class="relative flex flex-col max-w-[1400px] mx-auto w-full text-sm sm:text-base min-h-screen">
	<Header />
	<slot />
	<Footer />
</div>

<svelte:window bind:innerHeight bind:innerWidth />
