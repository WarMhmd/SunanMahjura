<script lang="ts">
	export let index: number = 0;
	export let header: string = '';
	export let body: string = '';

	let opened = false;

	$: body = body.trim().replaceAll('\n', '<br/>');
</script>

<div class="card | VerticalStack">
	<button on:click={() => (opened = !opened)} class="header | HorizontalStack center">
		<div class="HorizontalStack center">
			<div class="circle">{('0' + (index + 1)).slice(-2)}</div>
			<h2>{header}</h2>
		</div>
		<div class="arrow" class:opened>
			<!-- prettier-ignore -->
			<svg xmlns="http://www.w3.org/2000/svg" width="15" height="15" viewBox="0 0 15 15"><path fill="none" stroke="currentColor" stroke-linecap="square" d="m14 5l-6.5 7L1 5"/></svg>
		</div>
	</button>
	<div class="body" class:opened>
		<p>{@html body}</p>
	</div>
</div>

<style>
	.card {
		gap: 2rem;
		isolation: isolate;
		overflow: hidden;
	}

	.card .header {
		justify-content: space-between;
		font-size: 1rem;

		background-color: rgb(var(--clr-primary));
		color: rgb(var(--clr-background));

		padding: 2rem;
		border-radius: 0.5rem;

		cursor: pointer;
	}

	.card .header h2 {
		flex: 1;
	}

	.card .header .circle {
		display: flex;
		justify-content: center;
		align-items: center;

		font-weight: bold;

		width: 2rem;
		height: 2rem;
		min-height: 2rem;
		max-height: 2rem;
		border-radius: 999rem;

		border: 1px solid rgb(var(--clr-background));
	}

	.card .header .arrow {
		width: 1rem;
		min-height: 1rem;

		color: rgb(var(--clr-background));
		transition: all 0.2s ease-out;
	}
	.card .header .arrow.opened {
		transform: rotate(180deg);
	}

	.card .body {
		display: none;

		background-color: rgb(var(--clr-primary));
		color: rgb(var(--clr-background));

		padding: 2rem;
		border-radius: 0.5rem;
		line-height: 1.5;
	}

	.card .body.opened {
		position: relative;
		z-index: -1;
		display: block;
		transform-origin: top center;
		animation: open 0.3s cubic-bezier(0.165, 0.84, 0.44, 1);
	}

	@media (max-width: 40em) {
		.card {
			gap: 1rem;
		}
		.card .header {
			font-size: 1rem;
			padding: 1rem;
		}

		.card .body {
			padding: 1rem;
			font-size: 0.75rem;
			line-height: 1.75;
		}
	}

	@keyframes open {
		from {
			opacity: 0;
			transform: translate(0, -100%);
		}
		to {
			opacity: 1;
			transform: translate(0, 0);
		}
	}
</style>
