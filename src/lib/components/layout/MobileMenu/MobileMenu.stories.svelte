<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import MobileMenu from './MobileMenu.svelte';

	const { Story } = defineMeta({
		component: MobileMenu,
		tags: ['autodocs'],
		title: 'Layout/Hamburger Menu'
	});
</script>

<Story name="Mobile Nav Menu" />
