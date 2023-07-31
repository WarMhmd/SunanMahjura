<script lang="ts">
	import Card from '$lib/components/Card.svelte';
	import Container from '$lib/components/Container.svelte';
	import data from '$lib/data.json';

	let HeroAccentImage: string;
</script>

<section class="heroSection">
	<Container>
		<div class="heroLayout">
			<!-- <span /> -->
			<span>استعادة السنن المهجورة في حياتنا اليومية</span>
			<h1 class="fs-text-h1">إحياء للسنة</h1>
			<p class="fs-text-body">
				هي مبادرة انطلقت من قوله صلى الله عليه وسلم ( من أحيا سنة من سنتي فعمل بها الناس كان له مثل
				أجر من عمل بها لا ينقص من أجورهم شيئا)
			</p>
			<a href="#hadith" class="arrow">
				<!-- prettier-ignore -->
				<svg xmlns="http://www.w3.org/2000/svg" width="36" height="36" viewBox="0 0 36 36"><g transform="rotate(180 18 18)"><path fill="currentColor" d="M18 2a16 16 0 1 0 16 16A16 16 0 0 0 18 2Zm0 30a14 14 0 1 1 14-14a14 14 0 0 1-14 14Z" class="clr-i-outline clr-i-outline-path-1"/><path fill="currentColor" d="m18.08 8.26l-7.61 7.61a1 1 0 1 0 1.41 1.41l5.12-5.1v15a1 1 0 0 0 2 0V12l5.28 5.28a1 1 0 1 0 1.41-1.41Z" class="clr-i-outline clr-i-outline-path-2"/><path fill="none" d="M0 0h36v36H0z"/></g></svg>
			</a>
		</div>
	</Container>
	<div class="HeroAccent" data-src={HeroAccentImage} />
</section>

<section id="hadith">
	<Container>
		<div class="hadithLayout | VerticalStack">
			<div class="VerticalStack center">
				<h2 class="fs-text-h2">السنن المهجورة</h2>
				<p class="fs-text-body">
					تعتبر السنن المهجورة من العادات والتقاليد النبوية التي تم تجاهلها أو تركها على مر الزمان
					في حياة المسلمين.
				</p>
			</div>
			<div class="cardsHolder | VerticalStack">
				{#each data as item, index}
					<Card {index} header={item.header} body={item.body} />
				{/each}
			</div>
		</div>
	</Container>
</section>

<section />

<style>
	.heroSection {
		position: relative;
		isolation: isolate;

		overflow: hidden;
	}

	.heroLayout {
		position: relative;
		isolation: isolate;

		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		gap: 1rem;

		height: 100vh;
		color: rgb(var(--clr-background));
	}
	.heroLayout > span {
		font-size: 1rem;
		font-weight: 400;

		opacity: 0.9;
	}

	.heroLayout > h1 {
		font-weight: 600;
	}

	.heroLayout > p {
		font-weight: 400;
		opacity: 0.8;
	}

	p {
		max-width: 40rem;
		text-align: center;
	}

	.heroLayout > .arrow {
		position: absolute;
		bottom: 2rem;

		color: rgba(255, 255, 255, 0.7);

		cursor: pointer;
		transition: all 0.2s ease-out;
	}

	.heroLayout > .arrow:hover {
		color: rgba(255, 255, 255, 1);
	}

	.HeroAccent {
		position: absolute;
		inset: 0;
		z-index: -1;

		background-color: rgba(var(--clr-primary), 0.9);
		background-image: url('/background1.jpg');
		background-size: cover;
		background-repeat: no-repeat;
		background-position: center;
		background-blend-mode: multiply;
	}

	.hadithLayout {
		gap: 4rem;
	}

	.cardsHolder {
		gap: 2rem;
	}
</style>
