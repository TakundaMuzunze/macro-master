<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import CtaBanner from './CtaBanner.svelte';

	const { Story } = defineMeta({
		component: CtaBanner,
		tags: ['autodocs'],
		title: 'Sections/Banners/CTA Banner'
	});
</script>

<Story name="CTA Banner Component" />
