<script lang="ts">
	import Marquee from 'svelte-fast-marquee';

	type Feature = {
		icon: string;
		title: string;
		description: string;
	};

	const features: Feature[] = [
		{
			icon: '📊',
			title: 'Macro Tracking',
			description: 'Auto-calculates your daily targets based on goals.'
		},
		{
			icon: '🛒',
			title: 'Smart Shopping List',
			description: 'Export ingredients by meal or day.'
		},
		{
			icon: '⚡',
			title: 'Quick Meal Swaps',
			description: 'Instantly replace ingredients based on macros.'
		}
	];
</script>

<Marquee pauseOnHover="true" speed="30" gradientWidth="20" gradientColor="#000000">
	{#each features as feature}
		<article
			class="bg-surface ml-5 flex flex-col items-center justify-center gap-1 rounded-2xl p-4"
		>
			<p>{feature.icon}</p>
			<h2 class="text-primary">{feature.title}</h2>
			<p class="text-primary text-base">{feature.description}</p>
		</article>
	{/each}
</Marquee>
