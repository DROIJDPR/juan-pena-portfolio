<script lang="ts">
	import '$lib/styles/sections/about.css';
	import Reveal from '$lib/components/ui/Reveal.svelte';
</script>

<Reveal>
<section id="about" class="about">
	<div class="about-header">
		<p class="section-label">About</p>

		<h2>About Me</h2>
	</div>

	<div class="about-content">
		<p>
			I’m a Computer Science student at Universidad del Sagrado Corazón with a passion for building
			modern, responsive and user-friendly web applications.
		</p>

		<div class="about-cards">
			<div class="about-card">
				<h3>Frontend</h3>

				<p>SvelteKit, TypeScript, JavaScript and CSS.</p>
			</div>

			<div class="about-card">
				<h3>UI / UX</h3>

				<p>Clean, modern and responsive interfaces.</p>
			</div>

			<div class="about-card">
				<h3>AI</h3>

				<p>Interested in AI-powered web applications.</p>
			</div>
		</div>
	</div>
</section>
</Reveal>
