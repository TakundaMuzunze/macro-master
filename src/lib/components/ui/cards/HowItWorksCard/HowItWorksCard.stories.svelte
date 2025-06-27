<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import HowItWorksCard from './HowItWorksCard.svelte';

	const { Story } = defineMeta({
		component: HowItWorksCard,
		tags: ['autodocs'],
		title: 'Cards/How it Works',

		argTypes: {
			icon: {
				control: 'text'
			},
			title: {
				control: 'text'
			},
			text: {
				control: 'text'
			}
		}
	});
</script>

<Story name="How it Works Card Component" />
