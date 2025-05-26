<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import Button from './Button.svelte';

	const { Story } = defineMeta({
		component: Button,
		tags: ['autodocs'],
		argTypes: {
			variant: {
				control: { type: 'select' },
				options: ['primary', 'secondary', 'ghost']
			},
			size: {
				control: { type: 'select' },
				options: ['sm', 'md', 'lg']
			},
			text: {
				control: 'text'
			}
		}
	});
</script>

<Story name="Base Button" />
