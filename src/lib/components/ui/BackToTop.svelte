<script lang="ts">
	function scrollToTop() {
		window.scrollTo({
			top: 0,
			behavior: 'smooth'
		});
	}
</script>

<button class="back-to-top" onclick={scrollToTop} aria-label="Back to top"> ↑ </button>

<style>
	.back-to-top {
		position: fixed;

		right: 2rem;
		bottom: 2rem;

		width: 50px;
		height: 50px;

		border: none;

		border-radius: 50%;

		cursor: pointer;

		font-size: 1.2rem;

		background: linear-gradient(135deg, #3b82f6, #8b5cf6);

		color: white;

		box-shadow: 0 10px 25px rgba(59, 130, 246, 0.3);

		transition: all 0.2s ease;

		z-index: 100;
	}

	.back-to-top:hover {
		transform: translateY(-3px);
	}
</style>
