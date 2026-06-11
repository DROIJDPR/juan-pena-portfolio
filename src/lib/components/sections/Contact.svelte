<script lang="ts">
	import '$lib/styles/sections/contact.css';
	import { Mail } from '@lucide/svelte/icons';
	import GithubIcon from '$lib/components/icons/GithubIcon.svelte';
	import LinkedinIcon from '$lib/components/icons/LinkedinIcon.svelte';
	import { fly } from 'svelte/transition';
</script>

<section id="contact" class="contact" in:fly={{ duration: 700 }}>
	<p class="section-label">Contact</p>

	<h2>Let's Work Together</h2>

	<p class="contact-description">
		I'm always interested in new opportunities, collaborations and learning experiences.
	</p>

	<div class="contact-links">
		<a href="mailto:tuemail@example.com">
			<Mail size={18} />
			Email
		</a>

		<a href="https://github.com/DROIJDPR" target="_blank" rel="noopener noreferrer">
			<GithubIcon size={18} />
			GitHub
		</a>

		<a href="https://linkedin.com" target="_blank" rel="noopener noreferrer">
			<LinkedinIcon size={18} />
			LinkedIn
		</a>
	</div>
</section>
