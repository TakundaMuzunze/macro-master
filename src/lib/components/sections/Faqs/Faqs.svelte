<script lang="ts">
	import ChevronIcon from '$lib/components/icons/ChevronIcon/ChevronIcon.svelte';
	import { faqsContent } from '$lib/constants/faqs';

	let accordionIndex = -1;

	function toggleAccordion(index: number): void {
		accordionIndex = accordionIndex === index ? -1 : index;
	}
</script>

<section class="flex w-full flex-col items-center justify-center gap-5 p-10 lg:gap-10">
	<h2 class="text-primary text-center text-2xl text-balance lg:text-3xl">
		Frequently asked questions
	</h2>
	<div class="mx-auto flex w-full max-w-2xl flex-col gap-5 py-5 lg:py-10">
		{#each faqsContent as content, i}
			<div
				class={`border-1 transition-all duration-200 ease-in-out ${accordionIndex === i ? 'bg-surface border-surface' : 'border-primary'}  w-full rounded-2xl  p-5`}
			>
				<button
					onclick={() => toggleAccordion(i)}
					class="text-primary flex w-full cursor-pointer flex-row items-center justify-between text-left text-lg font-semibold lg:text-xl"
					>{content.title} <ChevronIcon />
				</button>
				<p class={`text-primary mt-5 font-light ${accordionIndex === i ? 'block' : 'hidden'} `}>
					{content.description}
				</p>
			</div>
		{/each}
	</div>
</section>
