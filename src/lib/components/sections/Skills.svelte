<script lang="ts">
	import '$lib/styles/sections/skills.css';
	import { fade } from 'svelte/transition';

	const skills = [
		'SvelteKit',
		'TypeScript',
		'JavaScript',
		'HTML5',
		'CSS3',
		'Git',
		'GitHub',
		'Vercel',
		'Responsive Design',
		'UI / UX'
	];
</script>

<section id="skills" class="skills" in:fade={{ duration: 600 }}>
	<p class="section-label">Skills</p>

	<h2>Technologies & Tools</h2>

	<div class="skills-grid">
		{#each skills as skill (skill)}
			<div class="skill-badge">
				{skill}
			</div>
		{/each}
	</div>
</section>
