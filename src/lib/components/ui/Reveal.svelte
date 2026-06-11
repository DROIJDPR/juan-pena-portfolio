<script lang="ts">
    import type { Snippet } from 'svelte';

	let {
		children
	}: {
		children?: Snippet;
	} = $props();

	let visible = $state(false);

	let element: HTMLElement;

	$effect(() => {
	const observer = new IntersectionObserver(
		([entry]) => {
			if (entry.isIntersecting) {
				visible = true;
				observer.disconnect();
			}
		},
		{
			threshold: 0.15
		}
	);

	if (element) {
		observer.observe(element);
	}

	return () => {
		observer.disconnect();
	};
});
</script>

<div
	bind:this={element}
	class:visible
	class="reveal"
>
	{@render children?.()}
</div>

<style>
	.reveal {
		opacity: 0;

		transform: translateY(30px);

		transition:
			opacity 0.8s ease,
			transform 0.8s ease;
	}

	.reveal.visible {
		opacity: 1;

		transform: translateY(0);
	}
</style>