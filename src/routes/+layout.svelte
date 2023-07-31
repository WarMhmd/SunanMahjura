<script>
</script>

<svelte:head>
	<link
		href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<div class="app">
	<header />

	<main>
		<slot />
	</main>

	<footer />
</div>

<style>
	:global(main) {
		/* height: 100%; */
		flex: 1;
	}
	:global(:root) {
		--clr-text: 0, 0, 0;
		--clr-background: 236, 238, 237;
		--clr-primary: 36, 73, 47;
		--clr-secondary: 169, 249, 193;
		--clr-accent: 70, 145, 92;

		--ff-primary: 'Tajawal', 'sans-serif';

		--ff-body: var(--ff-primary);

		--fw-light: 300;
		--fw-regular: 400;
		--fw-medium: 500;
		--fw-bold: 700;

		--fs-200: 0.236rem;
		--fs-300: 0.875rem;
		--fs-400: 1rem;
		--fs-450: 1.25rem;
		--fs-500: 1.5rem;
		--fs-600: 2rem;
		--fs-700: 2.25rem;
		--fs-800: 3rem;
		--fs-900: 4rem;

		--fs-text-h1: var(--fs-800);
		--fs-text-h2: var(--fs-700);
		--fs-text-h3: var(--fs-600);
		--fs-text-body: var(--fs-400);
		--fs-text-small: var(--fs-300);

		--fs-body: var(--fs-400);
		--fs-nav: var(--fs-500);
		--fs-button: var(--fs-400);
	}

	:global(body),
	:global(html) {
		width: 100%;
		height: 100%;
	}

	:global(*),
	:global(*::before),
	:global(*::after) {
		margin: 0;
		padding: 0;
		font: inherit;
		box-sizing: border-box;
	}

	/* Desktop min size */
	@media (min-width: 50em) {
		:root {
			--fs-text-h1: var(--fs-900);
			--fs-text-h2: var(--fs-800);
			--fs-text-h3: var(--fs-700);
			--fs-text-body: var(--fs-500);

			--fs-body: var(--fs-500);
			--fs-nav: var(--fs-500);
			--fs-button: var(--fs-500);
		}
	}

	:global(input):focus,
	:global(select):focus,
	:global(textarea):focus,
	:global(button):focus {
		outline: none;
	}

	/* Remove list styles on ul, ol elements with a list role, which suggests default styling will be removed */
	:global(ul[role='list']),
	:global(ol[role='list']) {
		list-style: none;
	}

	/* Set core root defaults */
	:global(html) {
		scroll-behavior: smooth;
	}

	/* Set core body defaults */
	:global(body) {
		text-rendering: optimizeSpeed;
		line-height: 1.3;
	}

	/* A elements that don't have a class get default styles */
	:global(a:not([class])) {
		text-decoration-skip-ink: auto;
	}

	/* Make images easier to work with */
	:global(img),
	:global(picture),
	:global(svg) {
		max-width: 100%;
		display: block;
	}

	/* Remove all animations, transitions and smooth scroll for people that prefer not to see them */
	@media (prefers-reduced-motion: reduce) {
		:global(html:focus-within) {
			scroll-behavior: auto !important;
		}

		:global(*),
		:global(*::before),
		:global(*::after) {
			animation-duration: 0.01ms !important;
			animation-iteration-count: 1 !important;
			transition-duration: 0.01ms !important;
			scroll-behavior: auto !important;
		}
	}

	/* Utility classes */
	:global(.clr-primary) {
		--opacity: 1;
		color: rgba(var(--clr-primary), var(--opacity));
	}
	:global(.clr-secondary) {
		--opacity: 1;
		color: rgba(var(--clr-secondary), var(--opacity));
	}
	:global(.clr-accent) {
		--opacity: 1;
		color: rgba(var(--clr-accent), var(--opacity));
	}
	:global(.clr-text) {
		--opacity: 1;
		color: rgba(var(--clr-text), var(--opacity));
	}
	:global(.clr-background) {
		--opacity: 1;
		color: rgba(var(--clr-background), var(--opacity));
	}

	:global(.bg-primary) {
		--opacity: 1;
		background-color: rgba(var(--clr-primary), var(--opacity));
	}
	:global(.bg-secondary) {
		--opacity: 1;
		background-color: rgba(var(--clr-secondary), var(--opacity));
	}
	:global(.bg-accent) {
		--opacity: 1;
		background-color: rgba(var(--clr-accent), var(--opacity));
	}
	:global(.bg-text) {
		--opacity: 1;
		background-color: rgba(var(--clr-text), var(--opacity));
	}
	:global(.bg-background) {
		--opacity: 1;
		background-color: rgba(var(--clr-background), var(--opacity));
	}

	:global(.opacity-0) {
		--opacity: 0;
	}

	:global(.opacity-10) {
		--opacity: 0.1;
	}

	:global(.opacity-20) {
		--opacity: 0.2;
	}

	:global(.opacity-30) {
		--opacity: 0.3;
	}

	:global(.opacity-40) {
		--opacity: 0.4;
	}

	:global(.opacity-50) {
		--opacity: 0.5;
	}

	:global(.opacity-60) {
		--opacity: 0.6;
	}

	:global(.opacity-70) {
		--opacity: 0.7;
	}

	:global(.opacity-80) {
		--opacity: 0.8;
	}

	:global(.opacity-90) {
		--opacity: 0.9;
	}

	:global(.opacity-100) {
		--opacity: 1;
	}

	:global(.fw-light) {
		font-weight: var(--fw-light);
	}
	:global(.fw-regular) {
		font-weight: var(--fw-regular);
	}
	:global(.fw-medium) {
		font-weight: var(--fw-medium);
	}
	:global(.fw-bold) {
		font-weight: var(--fw-bold);
	}

	:global(.ff-primary) {
		font-family: var(--ff-primary);
	}

	:global(.fs-200) {
		font-size: var(--fs-200);
	}
	:global(.fs-300) {
		font-size: var(--fs-300);
	}
	:global(.fs-400) {
		font-size: var(--fs-400);
	}
	:global(.fs-450) {
		font-size: var(--fs-450);
	}
	:global(.fs-500) {
		font-size: var(--fs-500);
	}
	:global(.fs-600) {
		font-size: var(--fs-600);
	}
	:global(.fs-700) {
		font-size: var(--fs-700);
	}
	:global(.fs-800) {
		font-size: var(--fs-800);
	}
	:global(.fs-900) {
		font-size: var(--fs-900);
	}

	/* :global(.padding-200) {
		padding: var(--fs-200);
	}
	:global(.padding-300) {
		padding: var(--fs-300);
	} */
	:global(.padding-400) {
		padding: var(--fs-400);
	}
	:global(.padding-500) {
		padding: var(--fs-500);
	}
	:global(.padding-600) {
		padding: var(--fs-600);
	}
	:global(.padding-700) {
		padding: var(--fs-700);
	}
	:global(.padding-800) {
		padding: var(--fs-800);
	}
	:global(.padding-900) {
		padding: var(--fs-900);
	}
	:global(.padding-block-400) {
		padding-block: var(--fs-400);
	}
	:global(.padding-block-500) {
		padding-block: var(--fs-500);
	}
	:global(.padding-block-600) {
		padding-block: var(--fs-600);
	}
	:global(.padding-block-700) {
		padding-block: var(--fs-700);
	}
	:global(.padding-block-800) {
		padding-block: var(--fs-800);
	}
	:global(.padding-block-900) {
		padding-block: var(--fs-900);
	}
	:global(.padding-inline-400) {
		padding-inline: var(--fs-400);
	}
	:global(.padding-inline-500) {
		padding-inline: var(--fs-500);
	}
	:global(.padding-inline-600) {
		padding-inline: var(--fs-600);
	}
	:global(.padding-inline-700) {
		padding-inline: var(--fs-700);
	}
	:global(.padding-inline-800) {
		padding-inline: var(--fs-800);
	}
	:global(.padding-inline-900) {
		padding-inline: var(--fs-900);
	}

	:global(.fs-text-h1) {
		font-size: var(--fs-text-h1);
		line-height: 1.2; /* 1.1 - 1.2 */
		letter-spacing: -1%;
	}
	:global(.fs-text-h2) {
		font-size: var(--fs-text-h2);
		line-height: 1.2;
		letter-spacing: -1%;
	}
	:global(.fs-text-h3) {
		font-size: var(--fs-text-h3);
		line-height: 1.2;
		letter-spacing: -1%;
	}
	:global(.fs-text-body) {
		font-size: var(--fs-text-body);
		line-height: 1.4; /*1.4 - 1.5*/
	}

	:global(.hidden) {
		display: none !important;
		opacity: 0;
		/* max-height: 0px !important; */
	}

	:global(a) {
		text-decoration: none;
		font: inherit;
		color: inherit;
	}

	/* general styling */
	:global(body) {
		position: relative;
		direction: rtl;
		font-family: var(--ff-body);
		font-weight: var(--fw-medium);
		color: var(--clr-neutral-800);

		background-color: rgb(var(--clr-background));
	}

	:global(.HorizontalStack) {
		display: flex;
		gap: 1rem;
	}

	:global(.VerticalStack) {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	:global(.TextCenter) {
		text-align: center;
	}

	:global(.HorizontalStack.center),
	:global(.VerticalStack.center) {
		align-items: center;
	}

	:global(.HorizontalStack.autospace),
	:global(.VerticalStack.autospace) {
		justify-content: space-between;
	}

	/* :global(.section) {
		padding-top: 2rem;
	}

	:global(.section:first) {
		padding: 0;
	} */

	:global(.noselect) {
		-webkit-touch-callout: none;
		-webkit-user-select: none;
		-khtml-user-select: none;
		-moz-user-select: none;
		-ms-user-select: none;
		user-select: none;
	}

	:global(.scroll) {
		overflow-y: auto;
	}

	:global(.scroll::-webkit-scrollbar) {
		width: 15px;
		cursor: context-menu;
	}

	:global(.scroll::-webkit-scrollbar-track) {
		/* margin-top: 5rem; */
		border-radius: 9999px;
		cursor: context-menu;
		/* background-color: black; */
	}

	:global(.scroll::-webkit-scrollbar-thumb) {
		box-shadow: inset 0 0 0 1px rgb(236, 236, 236);
		border: 4px solid rgba(0, 0, 0, 0);
		background-clip: padding-box;
		border-radius: 1000vmax;
		background-color: var(--clr-primary-500);
		cursor: context-menu;
	}

	:global(.scroll::-webkit-scrollbar-thumb:hover) {
		box-shadow: inset 0 0 0 1px white;
		background-color: var(--clr-primary-600);
	}

	:global(.relative) {
		position: relative;
	}

	:global([type='checkbox']) {
		display: none;
	}

	:global([data-isLoading='false'] > .OnlyLoading) {
		display: none;
	}

	:global([data-isLoading='true'] > .OnlyLoading) {
		display: block;
	}

	:global([data-isLoading='true'] > *:not(.OnlyLoading)) {
		display: none;
	}

	:global(button) {
		display: flex;
		place-content: center;
		justify-content: center;
		gap: 0.5rem;
		border-radius: 0.5rem;
		padding: 0;
		font-size: var(--fs-button);
		font-weight: var(--fw-normal);
		font-family: var(--ff-primary);
		background-color: transparent;
		border: none;

		/* line-height: 1.4; */
		cursor: pointer;
		transition: all 0.2s ease-out;
	}

	:global(section ~ section) {
		padding-top: 16rem;
	}

	:global(main + footer) {
		margin-top: 16rem;
	}

	@media (max-width: 50em) {
		:global(section ~ section) {
			padding-top: 8rem;
		}

		:global(main + footer) {
			margin-top: 8rem;
		}
	}
</style>
