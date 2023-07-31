<script lang="ts">
</script>

<div class="container">
	<slot />
</div>

<style>
	.container {
		--max-width: 90rem;
		--padding: 1rem;

		width: min(var(--max-width), 100% - 2 * var(--padding));
		margin-inline: auto;
	}

	@media (min-width: 50em) {
		.container {
			--padding: 4rem;

			width: min(var(--max-width), 100% - 2 * var(--padding));
		}
	}
</style>
