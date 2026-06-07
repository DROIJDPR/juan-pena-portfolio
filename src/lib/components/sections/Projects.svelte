<script lang="ts">
	import '$lib/styles/sections/projects.css';
	import ProjectCard from '$lib/components/ui/ProjectCard.svelte';
	import { fade } from 'svelte/transition';

	const projects = [
		{
			title: 'AI Flow Dashboard',
			description:
				'Responsive admin dashboard featuring analytics, user management, settings and a modern UI built with SvelteKit and TypeScript.',
			status: 'Live',
			technologies: ['SvelteKit', 'TypeScript', 'CSS', 'Vercel'],
			image: 'images/dashboard.png',
			github: 'https://github.com/DROIJDPR/ai-flow-dashboard',
			demo: 'https://ai-flow-dashboard.vercel.app/dashboard'
		},
		{
			title: 'Atrapa-Esfera',
			description: 'Arcade game project developed as a learning experience.',
			status: 'Completed'
		},
		{
			title: 'Portfolio Website',
			description: 'Personal portfolio built with Svelte 5 and TypeScript.',
			status: 'In Progress'
		}
	];
</script>

<section id="projects" class="projects" in:fade={{ duration: 600 }}>
	<p class="section-label">Projects</p>

	<h2>Featured Projects</h2>

	<div class="projects-grid">
		{#each projects as project (project.title)}
			<ProjectCard
				title={project.title}
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
