<script lang="ts">
	import type { Component } from 'svelte';

	let { title, icon, description }: { title: string; icon: Component; description: string } =
		$props();
</script>

<article
	class="bg-surface shadow-accent/30 flex h-full w-full flex-col items-center justify-center gap-6 rounded-2xl p-5 text-center transition-all ease-in-out hover:-translate-y-2 hover:shadow-md"
>
	<svelte:component this={icon} aria-hidden="true" />
	<h3 class="text-primary text-xl tracking-wider text-balance md:text-2xl">
		{title}
	</h3>
	<p class="text-primary font-light tracking-wide">{description}</p>
</article>
