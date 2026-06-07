<script lang="ts">
	import type { IconProps } from 'lucide-svelte';

	let {
		size = 24,
		color = 'currentColor',
		strokeWidth = 2,
		class: className = '',
		...restProps
	}: IconProps = $props();
</script>

<svg
	xmlns="http://w3.org"
	width={size}
	height={size}
	viewBox="0 0 24 24"
	fill="none"
	stroke={color}
	stroke-width={(Number(strokeWidth) * 24) / Number(size)}
	stroke-linecap="round"
	stroke-linejoin="round"
	class="lucide lucide-linkedin {className}"
	{...restProps}
>
	<path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z" />
	<rect width="4" height="12" x="2" y="9" />
	<circle cx="4" cy="4" r="2" />
</svg>
