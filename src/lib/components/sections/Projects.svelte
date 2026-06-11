<script lang="ts">
	import '$lib/styles/sections/projects.css';
	import ProjectCard from '$lib/components/ui/ProjectCard.svelte';
	import Reveal from '$lib/components/ui/Reveal.svelte';

	const projects = [
		{
			title: 'AI Flow Dashboard',
			year: '2026',
			description:
				'Interactive arcade game developed with React and TypeScript featuring score tracking, collision detection and responsive gameplay.',
			status: 'Live',
			technologies: ['SvelteKit', 'TypeScript', 'CSS', 'Vercel'],
			image: 'images/dashboard.png',
			github: 'https://github.com/DROIJDPR/ai-flow-dashboard',
			demo: 'https://ai-flow-dashboard.vercel.app/dashboard'
		},
		{
			title: 'Atrapa-Esfera',
			year: '2025',
			description: 'Arcade game project developed as a learning experience.',
			status: 'Completed',
			technologies: ['React', 'TypeScript', 'CSS'],
			github: ''
		},
		{
			title: 'Portfolio Website',
			year: '2025',
			description: 'Responsive portfolio built with Svelte 5, TypeScript and deployed on Vercel.',
			status: 'Live',
			technologies: ['Svelte 5', 'TypeScript', 'CSS', 'Vercel'],
			github: 'https://github.com/DROIJDPR/juan-pena-portfolio',
			demo: 'https://juan-pena-portfolio.vercel.app',
			image: 'images/portfolio.png'
		}
	];
</script>

<Reveal>
<section id="projects" class="projects">
	<p class="section-label">Projects</p>

	<h2>Featured Projects</h2>

	<div class="projects-grid">
		{#each projects as project (project.title)}
			<ProjectCard
				title={project.title}
				year={project.year}
				description={project.description}
				status={project.status}
				technologies={project.technologies}
				github={project.github}
				demo={project.demo}
				image={project.image}
			/>
		{/each}
	</div>
</section>
</Reveal>
