<script lang="ts">
	import { links } from '$lib/constants/navlinks';
	import { fly } from 'svelte/transition';

	let { event } = $props();
</script>

<div role="presentation" class="fixed inset-0 z-10 mx-auto bg-black/50 backdrop-blur-md"></div>

<div
	transition:fly|global={{ x: 20, duration: 200 }}
	class="bg-background-default fixed top-0 right-0 z-50 flex h-full w-1/2 flex-col items-center justify-center gap-5 p-5"
>
	<button
		onclick={event}
		class="text-primary-text absolute top-5 right-5 cursor-pointer"
		aria-label="Close menu"
	>
		<svg
			class="text-primary-text h-6 w-6"
			xmlns="http://www.w3.org/2000/svg"
			viewBox="0 0 24 24"
			stroke-width="1.5"
			stroke="currentColor"
		>
			<path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
		</svg>
	</button>

	<ul class="flex flex-col items-center gap-4">
		{#each links as link}
			<li class="hover:text-accent text-primary-text cursor-pointer lg:text-xl">{link.label}</li>
		{/each}
	</ul>
</div>
