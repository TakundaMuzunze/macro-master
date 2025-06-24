<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import MasonryGrid from './MasonryGrid.svelte';

	const { Story } = defineMeta({
		component: MasonryGrid,
		tags: ['autodocs'],
		title: 'Sections/Hero/Masonry Grid'
	});
</script>

<Story name="Hero Grid" />
