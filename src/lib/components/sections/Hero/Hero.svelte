<script>
	import Button from '$lib/components/ui/buttons/Button.svelte';
	import Marquee from './Marquee.svelte';
	import MasonryGrid from './MasonryGrid.svelte';
</script>

<section
	class="mx-auto flex min-h-screen w-full flex-col items-center justify-center gap-6 px-5 xl:px-10"
>
	<div class="flex w-full flex-col items-center justify-between gap-6 lg:flex-row">
		<div class="flex w-full flex-col gap-4 lg:w-1/2 xl:w-[40%]">
			<h1 class="text-primary text-3xl font-semibold capitalize md:text-4xl xl:text-5xl">
				Your <span class="text-primary-btn">smart</span> meal planning companion
			</h1>
			<p class="text-primary mb-0 font-normal md:text-lg lg:mb-8 xl:text-2xl">
				Built for gym-goers who train with purpose. Macro Master helps you generate daily meal
				plans, tweak ingredients, and stay on track with your calorie and macro goals. No guesswork,
				just gains.
			</p>
			<Button size="lg" variant="primary" event text="Get started now" />
		</div>
		<MasonryGrid />
	</div>
	<div class="mt-4 w-full lg:hidden">
		<Marquee />
	</div>
</section>
