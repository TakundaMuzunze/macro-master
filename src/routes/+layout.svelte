<script lang="ts">
	import Footer from '$lib/components/layout/Footer/Footer.svelte';
	import Header from '$lib/components/layout/Header/Header.svelte';
	import '../app.css';

	let { children } = $props();
</script>

<a
	href="#main-content"
	class="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4 focus:z-50 focus:rounded focus:bg-blue-600 focus:px-4 focus:py-2 focus:text-white focus:ring-2 focus:ring-blue-500 focus:outline-none"
>
	Skip to main content
</a>

<div class="relative min-h-screen">
	<Header />

	<main id="main-content" class="flex h-full flex-col gap-4 pt-[5rem] lg:gap-8">
		{@render children()}
	</main>

	<Footer />
</div>
