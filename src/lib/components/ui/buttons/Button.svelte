<script lang="ts">
	let { size, variant, event, text } = $props();

	const variants: Record<typeof variant, string> = {
		primary: 'bg-primary-btn rounded-lg text-primary-text',
		secondary: 'bg-secondary-btn rounded-lg text-primary-text',
		ghost: 'bg-transparent rounded-lg border-2 border-primary-btn text-primary-btn'
	};

	const buttonSizes: Record<typeof size, string> = {
		sm: 'px-4 py-2',
		md: 'px-6 py-3',
		lg: 'px-8 py-4'
	};
</script>

<button
	onclick={event}
	aria-label={text}
	class={` shadow-accent/80 inline-flex cursor-pointer items-center gap-2 rounded-2xl font-medium transition-all ease-in-out hover:-translate-y-1 hover:shadow-md
    ${variants[variant]} ${buttonSizes[size]}`}>{text}</button
>
