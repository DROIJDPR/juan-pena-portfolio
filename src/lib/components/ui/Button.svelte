<script lang="ts">
	import '$lib/styles/components/button.css';

	interface Props {
		label: string;
		variant?: 'primary' | 'secondary';
		href?: string;
	}

	let { label, variant = 'primary', href }: Props = $props();
</script>

{#if href}
	<a {href} class={`button ${variant}`}>
		{label}
	</a>
{:else}
	<button class={`button ${variant}`}>
		{label}
	</button>
{/if}
