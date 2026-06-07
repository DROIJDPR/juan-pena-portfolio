<script lang="ts">
	interface Props {
		title: string;
		description: string;
		status: string;
		github?: string;
		demo?: string;
		image?: string;
		technologies?: string[];
	}

	let { title, description, status, github, demo, technologies = [], image }: Props = $props();
</script>

<div class="project-card">
	<div class="project-image">
		{#if image}
			<img src={image} alt={title} />
		{:else}
			Project Preview
		{/if}
	</div>
	<span class="status">
		{status}
	</span>

	<h3>
		{title}
	</h3>

	<p>
		{description}
	</p>

	<div class="tech-list">
		{#each technologies as tech (tech)}
			<span class="tech">
				{tech}
			</span>
		{/each}
	</div>

	<div class="project-links">
		{#if demo}
			<a href={demo} target="_blank" rel="noopener noreferrer"> Live Demo </a>
		{/if}

		{#if github}
			<a href={github} target="_blank" rel="noopener noreferrer"> GitHub </a>
		{/if}
	</div>
</div>
