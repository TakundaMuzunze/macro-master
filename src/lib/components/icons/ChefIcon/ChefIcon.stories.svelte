<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import ChefIcon from './ChefIcon.svelte';

	const { Story } = defineMeta({
		component: ChefIcon,
		tags: ['autodocs'],
		title: 'Icons/Auto Generate Meal Icon'
	});
</script>

<Story name="Chef Hat Icon" />
