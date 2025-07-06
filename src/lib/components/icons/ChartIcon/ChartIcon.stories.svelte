<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import ChartIcon from './ChartIcon.svelte';

	const { Story } = defineMeta({
		component: ChartIcon,
		tags: ['autodocs'],
		title: 'Icons/Chart Icon'
	});
</script>

<Story name="Graph Icon" />
