<script lang="ts">
	import '$lib/styles/sections/hero.css';
	import { fade } from 'svelte/transition';
	import Button from '$lib/components/ui/Button.svelte';
</script>

<section id="home" class="hero" in:fade={{ duration: 600 }}>
	<div class="hero-content">
		<div class="hero-badge">Computer Science Student</div>

		<p class="hero-intro">Hello, I’m</p>

		<h1>Juan Peña</h1>

		<h2>Computer Science Student • Frontend Developer</h2>

		<p class="hero-description">
			I'm a Computer Science student passionate about building modern, responsive and user-focused
			web applications using SvelteKit, TypeScript and modern development practices.
		</p>

		<div class="hero-details">
	<span>📍 Puerto Rico</span>
	<span>🎓 Universidad del Sagrado Corazón</span>
	<span>💻 Focused on Web Development</span>
</div>

		<div class="hero-stats">
			<div class="stat">
				<span class="stat-number">3+</span>
				<span class="stat-label">Projects</span>
			</div>

			<div class="stat">
				<span class="stat-number">1</span>
				<span class="stat-label">Live Dashboard</span>
			</div>

			<div class="stat">
				<span class="stat-number">4+</span>
				<span class="stat-label">Technologies</span>
			</div>
		</div>

		<div class="hero-actions">
	<Button label="View Projects" href="#projects" />

	<Button label="Contact Me" href="#contact" variant="secondary" />
		<a
			href="/JuanPenaResume2026.pdf"
			target="_blank"
			rel="noopener noreferrer"
			class="button secondary"
		>
			📄 Resume
		</a>
</div>
	</div>

	<div class="hero-visual">
		<div class="avatar">
			<img src="/images/avatar.png" alt="Juan Peña" />
		</div>
	</div>
</section>
