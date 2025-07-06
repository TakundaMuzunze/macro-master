<script>
	import FeatureCard from '$lib/components/ui/cards/FeatureCard/FeatureCard.svelte';
	import { featuresHighlights } from '$lib/constants/features';
</script>

<section
	class="relative flex w-full flex-col items-center justify-center gap-6 p-5 lg:p-10"
	aria-labelledby="feature-title"
>
	<h2
		id="feature-title"
		class="text-primary px-5 text-center text-2xl font-normal text-balance md:text-3xl lg:text-4xl"
	>
		Why MacroMaster is for you
	</h2>
	<p class="text-primary text-center text-lg font-light">
		Strong features to assist you in creating dishes and tracking your calories
	</p>

	<div
		class="flex w-full max-w-4xl gap-4 overflow-x-auto scroll-smooth px-4 py-4 md:grid md:grid-cols-2 md:py-8 lg:gap-6 lg:py-10"
		role="list"
		aria-label="Features for using the MacroMaster"
	>
		{#each featuresHighlights as feature}
			<div role="listitem" class="shrink-0">
				<FeatureCard {feature} />
			</div>
		{/each}
	</div>
</section>
