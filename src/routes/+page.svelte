<script lang="ts">
	import Sidebar from '$lib/components/layout/Sidebar.svelte';
	import Hero from '$lib/components/sections/Hero.svelte';
	import About from '$lib/components/sections/About.svelte';
	import Skills from '$lib/components/sections/Skills.svelte';
	import Projects from '$lib/components/sections/Projects.svelte';
	import Contact from '$lib/components/sections/Contact.svelte';
	import Footer from '$lib/components/layout/Footer.svelte';
	import BackToTop from '$lib/components/ui/BackToTop.svelte';
	import Journey from '$lib/components/sections/Journey.svelte';
</script>

<Sidebar />

<main class="content">
	<Hero />
	<About />
	<Journey />
	<Skills />
	<Projects />
	<Contact />
	<Footer />
	<BackToTop />
</main>

<style>
	.content {
		margin-left: 220px;
	}

	@media (max-width: 1024px) {
		.content {
			margin-left: 0;
		}
	}
</style>
