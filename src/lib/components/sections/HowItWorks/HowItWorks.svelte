<script lang="ts">
	import ChefIcon from '$lib/components/icons/ChefIcon/ChefIcon.svelte';
	import ClipboardIcon from '$lib/components/icons/ClipboardIcon/ClipboardIcon.svelte';
	import PreferenceIcon from '$lib/components/icons/PreferencesIcon/PreferenceIcon.svelte';
	import ShareIcon from '$lib/components/icons/ShareIcon/ShareIcon.svelte';
	import SwapIcon from '$lib/components/icons/SwapIcon/SwapIcon.svelte';
	import TargetIcon from '$lib/components/icons/TargetIcon/TargetIcon.svelte';
	import HowItWorksCard from '$lib/components/ui/cards/HowItWorksCard/HowItWorksCard.svelte';
	import type { Component } from 'svelte';

	type Step = {
		icon: Component;
		title: string;
		description: string;
	};

	const steps: Step[] = [
		{
			icon: TargetIcon,
			title: 'Set Your Macro Targets',
			description:
				'Define your daily calorie, protein, carbs, and fat goals manually or with a built-in calculator.'
		},
		{
			icon: PreferenceIcon,
			title: 'Pick Your Preferences',
			description:
				'Customize budget per meal, cooking time, dietary restrictions, and prep style like batch-cook or microwave-friendly.'
		},
		{
			icon: ChefIcon,
			title: 'Auto-Generate Your Meal Plan',
			description:
				"Instantly get a full day's worth of meals (3-6 per day) that align with your targets, with detailed breakdowns."
		},
		{
			icon: SwapIcon,
			title: 'Customize with Smart Swaps',
			description:
				"Don't like something? Swap ingredients—like salmon for tofu—and see your macros update live."
		},
		{
			icon: ClipboardIcon,
			title: 'Export a Smart Shopping List',
			description: 'One click to generate a clear, organized shopping list based on your meal plan.'
		},
		{
			icon: ShareIcon,
			title: 'Save & Share Your Plans',
			description: 'Easily save your plan for later or share it with friends or coaches.'
		}
	];
</script>

<section
	class="lG:p-10 relative flex w-full flex-col items-center justify-center gap-6 p-5"
	aria-labelledby="how-it-works-title"
>
	<h2
		id="how-it-works-title"
		class="text-primary px-5 text-center text-2xl font-normal text-balance md:text-3xl xl:text-4xl"
	>
		How does MacroMaster work?
	</h2>
	<p class="text-primary text-lg font-light">Learn how this app works</p>

	<div
		class="flex w-full gap-4 overflow-x-auto scroll-smooth px-4 py-4 md:py-8 lg:grid lg:grid-cols-3 lg:gap-6 lg:py-10"
		role="list"
		aria-label="Step-by-step process for using MacroMaster"
	>
		{#each steps as step}
			<div class="max-w-2xs shrink-0 md:max-w-xs xl:max-w-3xl" role="listitem">
				<HowItWorksCard {...step} />
			</div>
		{/each}
	</div>
</section>
