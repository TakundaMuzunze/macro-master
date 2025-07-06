<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import FeatureCard from './FeatureCard.svelte';

	const { Story } = defineMeta({
		component: FeatureCard,
		tags: ['autodocs'],
		title: 'Cards/Feature Card'
	});
</script>

<Story name="Feature Card Highlight" />
