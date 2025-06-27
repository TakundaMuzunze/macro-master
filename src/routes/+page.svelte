<script>
	import Header from '$lib/components/layout/Header/Header.svelte';
	import Hero from '$lib/components/sections/Hero/Hero.svelte';
	import HowItWorks from '$lib/components/sections/HowItWorks/HowItWorks.svelte';
</script>

<a
	href="#main-content"
	class="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4 focus:z-50 focus:rounded focus:bg-blue-600 focus:px-4 focus:py-2 focus:text-white focus:ring-2 focus:ring-blue-500 focus:outline-none"
>
	Skip to main content
</a>

<div class="relative min-h-screen">
	<Header />

	<main id="main-content" class="flex h-full flex-col pt-[5rem]">
		<Hero />
	</main>

	<HowItWorks />
</div>
