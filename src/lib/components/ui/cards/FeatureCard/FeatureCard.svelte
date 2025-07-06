<script lang="ts">
	let { feature } = $props();
</script>

<article
	class="bg-surface shadow-accent/30 flex h-full max-w-2xs flex-col items-center justify-center gap-6 rounded-2xl px-5 py-10 text-center transition-all ease-in-out hover:-translate-y-2 hover:shadow-md md:max-w-xs lg:max-w-2xl"
>
	<p class="text-primary text-4xl font-light tracking-wide">{feature.icon}</p>
	<h3 class="text-primary text-xl tracking-wider text-balance md:text-2xl">
		{feature.title}
	</h3>
	<p class="text-primary font-light tracking-wide">{feature.description}</p>
</article>
