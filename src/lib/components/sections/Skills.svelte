<script lang="ts">
	import '$lib/styles/sections/skills.css';
	import { fade } from 'svelte/transition';
	
	let visible = $state(false);

	function observeVisibility(node: HTMLElement) {
		const observer = new IntersectionObserver(
			(entries) => {
				if (entries[0].isIntersecting) {
					visible = true;
				}
			},
			{
				threshold: 0.3
			}
		);

		observer.observe(node);

		return {
			destroy() {
				observer.disconnect();
			}
		};
	}
	const skills = [
	{ name: 'SvelteKit', level: 80 },
	{ name: 'TypeScript', level: 75 },
	{ name: 'JavaScript', level: 80 },
	{ name: 'HTML5', level: 85 },
	{ name: 'CSS3', level: 85 },
	{ name: 'Git', level: 70 },
	{ name: 'GitHub', level: 75 },
	{ name: 'Vercel', level: 70 }
];
</script>

<section
	id="skills"
	class="skills"
	use:observeVisibility
	in:fade={{ duration: 600 }}
>
	<p class="section-label">Skills</p>

	<h2>Technical Skills</h2>

	<p class="skills-subtitle">
		Technologies and tools I've been using throughout my projects and coursework.
	</p>

	<div class="skills-list">
	{#each skills as skill (skill.name)}
		<div class="skill">
			<div class="skill-header">
				<span>{skill.name}</span>
				<span>{skill.level}%</span>
			</div>

			<div class="skill-bar">
				<div
				class="skill-progress"
				style={`width: ${visible ? skill.level : 0}%`}
			></div>
			</div>
		</div>
	{/each}
</div>
</section>
