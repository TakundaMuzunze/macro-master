<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import ThemeToggle from './ThemeToggle.svelte';

	const { Story } = defineMeta({
		component: ThemeToggle,
		tags: ['autodocs'],
		title: 'Toggles/Toggle Switch'
	});
</script>

<Story name="Theme Switch" />
