<script lang="ts">
	import { appState } from '$lib/stores/appState.stores.svelte';
	import { fly } from 'svelte/transition';
	import { links } from '$lib/constants/navlinks';
	import ThemeToggle from '$lib/components/ui/toggles/ThemeToggle.svelte';
	import MobileMenu from '../MobileMenu/MobileMenu.svelte';

	function toggleMenu(): void {
		appState.isMenuOpen = !appState.isMenuOpen;
	}
</script>

<header
	aria-label="Application header and navigation"
	class="bg-background-default fixed top-0 z-1 flex w-full flex-row items-center justify-between p-5"
>
	<div class="flex items-start justify-start">
		<h1 class="text-primary-text text-2xl">MacroMaster</h1>
	</div>

	<ul aria-label="Navigation links" class="flex flex-row gap-5 max-lg:hidden">
		{#each links as link}
			<li class="hover:text-accent text-primary-text cursor-pointer lg:text-xl">
				<a href={link.href}>{link.label}</a>
			</li>
		{/each}
	</ul>

	<div class="flex items-center gap-4">
		<ThemeToggle />

		<button
			aria-label="Toggle navigation menu"
			onclick={toggleMenu}
			class="w-6 cursor-pointer lg:hidden"
		>
			<svg class="fill-primary-text size-6" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
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
