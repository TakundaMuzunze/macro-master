<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import ValueBanner from './ValueBanner.svelte';

	const { Story } = defineMeta({
		component: ValueBanner,
		tags: ['autodocs'],
		title: 'Sections/Banners/Value Banner'
	});
</script>

<Story name="Value Banner Component" />
