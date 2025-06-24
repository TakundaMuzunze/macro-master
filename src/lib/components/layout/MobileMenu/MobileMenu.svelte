<script lang="ts">
	import { links } from '$lib/constants/navlinks';
	import { fly } from 'svelte/transition';
	import { onMount } from 'svelte';
	import { appState } from '$lib/stores/appState.stores.svelte';

	let { event } = $props();
	let closeButton: HTMLButtonElement;

	onMount(() => {
		if (closeButton) {
			closeButton.focus();
		}
	});

	function handleKeydown(event: KeyboardEvent) {
		if (event.key === 'Escape') {
			appState.isMenuOpen = false;
		}
	}
</script>

<!-- Backdrop -->
<div
	role="presentation"
	class="fixed inset-0 z-10 mx-auto bg-black/50 backdrop-blur-md"
	onclick={event}
	aria-hidden="true"
></div>

<!-- Mobile Menu -->
<div
	id="mobile-menu"
	role="dialog"
	aria-modal="true"
	aria-label="Mobile navigation menu"
	tabindex="0"
	transition:fly|global={{ x: 20, duration: 200 }}
	class="bg-background-default fixed top-0 right-0 z-50 flex h-full w-1/2 flex-col items-center justify-center gap-5 p-5"
	onkeydown={handleKeydown}
>
	<button
		bind:this={closeButton}
		onclick={event}
		class="text-primary absolute top-5 right-5 cursor-pointer rounded p-1 focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 focus:outline-none"
		aria-label="Close navigation menu"
	>
		<svg
			class="text-primary h-6 w-6"
			xmlns="http://www.w3.org/2000/svg"
			viewBox="0 0 24 24"
			stroke-width="1.5"
			stroke="currentColor"
			aria-hidden="true"
		>
			<path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
		</svg>
	</button>

	<nav aria-label="Mobile navigation">
		<ul class="flex flex-col items-center gap-4">
			{#each links as link}
				<li>
					<a
						href={link.href}
						class="hover:text-accent text-primary-text cursor-pointer rounded px-4 py-2 focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 focus:outline-none lg:text-xl"
						onclick={event}
					>
						{link.label}
					</a>
				</li>
			{/each}
		</ul>
	</nav>
</div>
