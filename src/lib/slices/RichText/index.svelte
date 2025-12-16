<script lang="ts">
	import type { Content } from '@prismicio/client';
	import { PrismicRichText, type SliceComponentProps } from '@prismicio/svelte';
	import Label from './Label.svelte';

	type Props = SliceComponentProps<Content.RichTextSlice>;

	const { slice }: Props = $props();
</script>

<section class="container">
	<span class="eyebrow">{slice.primary.eyebrow}</span>
	<PrismicRichText
		field={slice.primary.content}
		components={{
			label: Label
		}}
	/>
</section>

<style>
	.container {
		max-width: 600px;
		margin: 6em auto;
		font-family:
			-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif,
			'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol';
	}

	.eyebrow {
		font-size: 1.25rem;
		font-weight: 600;
		color: #666;
		margin-bottom: 1rem;
		outline: 1px solid red;
	}
</style>
