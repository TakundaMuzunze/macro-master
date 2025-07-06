<script>
	import FeatureCard from '$lib/components/ui/cards/FeatureCard/FeatureCard.svelte';
	import { featuresHighlights } from '$lib/constants/features';
</script>

<section
	class="relative flex w-full flex-col items-center justify-center gap-6 p-10"
	aria-labelledby="feature-title"
>
	<h2 id="feature-title" class="text-primary text-center text-4xl font-normal text-balance">
		Why MacroMaster is for you
	</h2>
	<p class="text-primary text-lg font-light italic">
		Strong features to assist you in creating dishes and tracking your calories
	</p>

	<div
		class="mx-auto grid w-full max-w-4xl grid-cols-2 flex-col gap-5 py-5 lg:py-10"
		role="list"
		aria-label="Step-by-step process for using MacroMaster"
	>
		{#each featuresHighlights as feature}
			<div role="listitem">
				<FeatureCard {feature} />
			</div>
		{/each}
	</div>
</section>
