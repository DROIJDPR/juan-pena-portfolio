<script lang="ts">
	import '$lib/styles/sections/journey.css';
	import { fly } from 'svelte/transition'

	const milestones = [
		{
			year: '2024',
			title: 'Started Computer Science',
			description: 'Began my Computer Science studies and software development journey.'
		},
		{
			year: '2025',
			title: 'Atrapa-Esfera',
			description: 'Built an arcade-style game as a learning project.'
		},
		{
			year: '2026',
			title: 'AI Flow Dashboard',
			description: 'Created a modern dashboard using SvelteKit and TypeScript.'
		},
		{
			year: '2026',
			title: 'Portfolio Website',
			description: 'Designed and developed a personal portfolio with Svelte 5.'
		}
	];
</script>

<section id="journey" class="journey" in:fly={{ y: 30, duration: 700}}>
	<p class="section-label">Journey</p>

	<h2>Education & Growth</h2>

	<div class="timeline">
		{#each milestones as milestone (milestone.title)}
			<div class="timeline-item">
				<div class="timeline-year">
					{milestone.year}
				</div>

				<div class="timeline-content">
					<h3>{milestone.title}</h3>

					<p>{milestone.description}</p>
				</div>
			</div>
		{/each}
	</div>
</section>
