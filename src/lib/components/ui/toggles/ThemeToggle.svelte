<script lang="ts">
	import { onMount } from 'svelte';

	let theme: 'light' | 'dark' = 'light';

	function toggleTheme() {
		theme = theme === 'light' ? 'dark' : 'light';
		document.documentElement.setAttribute('data-theme', theme);
		localStorage.setItem('theme', theme);
	}

	function handleKeydown(event: KeyboardEvent) {
		if (event.key === 'Enter' || event.key === ' ') {
			event.preventDefault();
			toggleTheme();
		}
	}

	onMount(() => {
		const savedTheme = localStorage.getItem('theme') as 'light' | 'dark' | null;
		if (savedTheme) {
			theme = savedTheme;
		}
		document.documentElement.setAttribute('data-theme', theme);
	});
</script>

<button
	on:click={toggleTheme}
	on:keydown={handleKeydown}
	aria-label="Toggle between light and dark theme. Currently {theme === 'light' ? 'light' : 'dark'} mode"
	aria-pressed={theme === 'dark'}
	class="relative flex h-10 w-20 items-center rounded-full bg-gray-200 px-2 transition-colors duration-300 dark:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2"
>
	<svg
		xmlns="http://www.w3.org/2000/svg"
		fill="none"
		viewBox="0 0 24 24"
		stroke-width="1.5"
		stroke="currentColor"
		class="absolute left-2 h-5 w-5 text-yellow-500"
		aria-hidden="true"
	>
		<path
			stroke-linecap="round"
			stroke-linejoin="round"
			d="M12 3v2.25m6.364.386l-1.591 1.591M21 12h-2.25m-.386 6.364l-1.591-1.591M12 18.75V21m-4.773-4.227l-1.591 1.591M5.25 12H3m4.227-4.773L5.636 5.636M15.75 12a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0z"
		/>
	</svg>

	<svg
		xmlns="http://www.w3.org/2000/svg"
		fill="none"
		viewBox="0 0 24 24"
		stroke-width="1.5"
		stroke="currentColor"
		class="absolute right-2 h-5 w-5 text-white"
		aria-hidden="true"
	>
		<path
			stroke-linecap="round"
			stroke-linejoin="round"
			d="M21.752 15.002A9.718 9.718 0 0118 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 003 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 009.002-5.998z"
		/>
	</svg>

	<!-- svelte-ignore element_invalid_self_closing_tag -->
	<span
		class="absolute z-10 h-6 w-6 rounded-full bg-white shadow-md transition-transform duration-350 dark:bg-gray-800"
		style="transform: translateX({theme === 'dark' ? '2.5rem' : '0rem'})"
		aria-hidden="true"
	/>
</button>
