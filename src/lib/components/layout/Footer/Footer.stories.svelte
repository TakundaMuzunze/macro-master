<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import Footer from './Footer.svelte';

	const { Story } = defineMeta({
		component: Footer,
		tags: ['autodocs'],
		title: 'Layout/Footer'
	});
</script>

<Story name="Footer Component" />
