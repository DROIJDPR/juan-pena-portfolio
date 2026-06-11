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
		rotating = true;
		
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
	class:theme-pop={rotating}
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

.theme-pop {
	animation: themePop 0.25s ease;
}

@keyframes themePop {
	0% {
		transform: scale(0.8);
	}

	50% {
		transform: scale(1.15);
	}

	100% {
		transform: scale(1);
	}
}

	@media (max-width: 1024px) {
		.floating-theme-toggle {
			top: 1rem;
			right: 1rem;
		}
	}
</style>