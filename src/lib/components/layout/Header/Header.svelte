<script lang="ts">
	import { appState } from '$lib/stores/appState.stores.svelte';
	import { links } from '$lib/constants/navlinks';
	import ThemeToggle from '$lib/components/ui/toggles/ThemeToggle.svelte';
	import MobileMenu from '../MobileMenu/MobileMenu.svelte';

	function toggleMenu(): void {
		appState.isMenuOpen = !appState.isMenuOpen;
	}

	function handleKeydown(event: KeyboardEvent) {
		if (event.key === 'Escape' && appState.isMenuOpen) {
			appState.isMenuOpen = false;
		}
	}
</script>

<svelte:window on:keydown={handleKeydown} />

<header
	aria-label="Main navigation"
	class="bg-background-default fixed top-0 z-2 flex w-full flex-row items-center justify-between px-4 pt-5 xl:px-10"
>
	<div class="flex items-start justify-start">
		<h1 class="text-primary text-2xl">
			<a
				href="/"
				class="hover:text-accent rounded focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 focus:outline-none"
			>
				MacroMaster
			</a>
		</h1>
	</div>

	<nav aria-label="Primary navigation" class="max-lg:hidden">
		<ul class="flex flex-row gap-5">
			{#each links as link}
				<li>
					<a
						href={link.href}
						class="hover:text-accent text-primary cursor-pointer rounded px-2 py-1 focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 focus:outline-none lg:text-xl"
					>
						{link.label}
					</a>
				</li>
			{/each}
		</ul>
	</nav>

	<div class="flex items-center gap-4">
		<ThemeToggle />

		<button
			aria-label="Toggle navigation menu"
			aria-expanded={appState.isMenuOpen}
			aria-controls="mobile-menu"
			on:click={toggleMenu}
			class="w-6 cursor-pointer rounded focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 focus:outline-none lg:hidden"
		>
			<svg
				class="fill-primary size-6"
				xmlns="http://www.w3.org/2000/svg"
				viewBox="0 0 448 512"
				aria-hidden="true"
			>
				<path
					d="M0 96C0 78.3 14.3 64 32 64l384 0c17.7 0 32 14.3 32 32s-14.3 32-32 32L32 128C14.3 128 0 113.7 0 96zM0 256c0-17.7 14.3-32 32-32l384 0c17.7 0 32 14.3 32 32s-14.3 32-32 32L32 288c-17.7 0-32-14.3-32-32zM448 416c0 17.7-14.3 32-32 32L32 448c-17.7 0-32-14.3-32-32s14.3-32 32-32l384 0c17.7 0 32 14.3 32 32z"
				/>
			</svg>
		</button>
	</div>

	{#if appState.isMenuOpen}
		<MobileMenu event={toggleMenu} />
	{/if}
</header>
