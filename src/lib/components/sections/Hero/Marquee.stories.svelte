<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import Marquee from './Marquee.svelte';

	const { Story } = defineMeta({
		component: Marquee,
		tags: ['autodocs'],
		title: 'Sections/Hero/Marquee'
	});
</script>

<Story name="Marquee Slideshow" />
