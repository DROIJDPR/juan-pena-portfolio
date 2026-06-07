<script lang="ts">
	import '$lib/styles/layout/sidebar.css';
	const links = ['Home', 'About', 'Skills', 'Projects', 'Contact'];

	let isOpen = $state(false);

	let activeSection = $state('home');

	$effect(() => {
		const sections = document.querySelectorAll('section');

		const observer = new IntersectionObserver(
			(entries) => {
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						activeSection = entry.target.id;
					}
				});
			},
			{
				threshold: 0.5
			}
		);

		sections.forEach((section) => observer.observe(section));

		return () => observer.disconnect();
	});
</script>

<button
	class="menu-toggle"
	class:hidden={isOpen}
	aria-label="Toggle menu"
	onclick={() => (isOpen = !isOpen)}
>
	☰
</button>

{#if isOpen}
	<button class="sidebar-overlay" aria-label="Close menu" onclick={() => (isOpen = false)}></button>
{/if}

<aside class="sidebar" class:open={isOpen}>
	<div class="sidebar-profile">
		<div class="sidebar-avatar">
			<img src="/images/avatar.png" alt="Juan Peña" />
		</div>

		<h2>Juan Peña</h2>

		<p>Computer Science Student</p>
		<a
			href="https://github.com/DROIJDPR"
			target="_blank"
			rel="noopener noreferrer"
			class="sidebar-github"
		>
			GitHub →
		</a>
	</div>

	<nav>
		{#each links as link (link)}
			<a
				href={'#' + link.toLowerCase()}
				class:active={activeSection === link.toLowerCase()}
				onclick={() => (isOpen = false)}
			>
				{link}
			</a>
		{/each}
	</nav>
</aside>
