<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import TargetIcon from './TargetIcon.svelte';

	const { Story } = defineMeta({
		component: TargetIcon,
		tags: ['autodocs'],
		title: 'Icons/Target'
	});
</script>

<Story name="Target Icon Component" />
