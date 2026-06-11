<script lang="ts">

	let rotating = $state(false);

	let theme = $state('dark');

	$effect(() => {
		const savedTheme = localStorage.getItem('theme');

		if (savedTheme === 'light') {
			theme = 'light';
			document.documentElement.setAttribute('data-theme', 'light');
		}
	});

	function toggleTheme() {
		theme = theme === 'dark' ? 'light' : 'dark';

		document.documentElement.setAttribute('data-theme', theme);

		localStorage.setItem('theme', theme);

		setTimeout(() => {
			rotating = false;
		}, 400);
	}
</script>

<button
	class="floating-theme-toggle"
	class:theme-rotate={rotating}
	onclick={toggleTheme}
	aria-label="Toggle theme"
>
	{theme === 'dark' ? '☀️' : '🌙'}
</button>

<style>
	.floating-theme-toggle {
		transform-origin: center;

		position: fixed;

		top: 1.5rem;
		right: 1.5rem;

		width: 48px;
		height: 48px;

		border-radius: 50%;

		border: 1px solid var(--border);

		background: var(--surface);

		color: var(--text);

		cursor: pointer;

		font-size: 1.25rem;

		z-index: 1000;

		transition:

		transform 0.2s ease,
		background-color 0.35s ease,
		border-color 0.35s ease,
		color 0.35s ease;
	}

	.floating-theme-toggle:hover {
		transform: translateY(-2px);

		border-color: var(--accent);
	}

	.theme-rotate {
	animation: themeSpin 0.4s ease;
}

@keyframes themeSpin {
	from {
		transform: rotate(0deg);
	}

	to {
		transform: rotate(180deg);
	}
}

	@media (max-width: 1024px) {
		.floating-theme-toggle {
			top: 1rem;
			right: 1rem;
		}
	}
</style>