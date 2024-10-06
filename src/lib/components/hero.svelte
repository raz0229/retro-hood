<script>
	import ArrowDown from '../svgs/arrow_down.svelte';
	import { slide } from 'svelte/transition';
    import ActionButton from './atoms/action-button.svelte';

	let animate = false;

	function actionWhenInViewport(e) {
		const observer = new IntersectionObserver((entries) => {
			if (entries[0].isIntersecting) {
				// element in viewport
				animate = true;
			} else {
				animate = false;
			}
		});

		observer.observe(e);
	}
</script>

<div use:actionWhenInViewport>
	{#if animate}
		<div
			transition:slide={{ duration: 1000 }}
			class="container flex flex-1 items-center sm:items-stretch p-16"
		>
			<div class="scroll-down flex flex-1 justify-end items-end mr-16">
				<div class="flex flex-col items-end justify-center" style="align-items: center;">
					<div class="arrow">
						<ArrowDown />
					</div>
					<div class="text" style="color: #c60203">Scroll down</div>
				</div>
			</div>
			<div class="hero-image flex-[3_3_0%] mt-36">
				<div class="image"></div>
				<div class="inner-text absolute top-[-7rem] left-[3rem]">
					<div class="welcome text-sm" style="color: #9f9f9f">Welcome here!</div>
					<div class="hero-text mt-3 text-4xl">
						We're a <br /> spark that <br /> <span class="fashion">fuels your</span> fashion brand
					</div>
					<ActionButton text='Get a quote'/>
				</div>
			</div>
		</div>
		<div transition:slide={{ duration: 1000 }} class="flex justify-center">
			<div
				class="main-text text-3xl text-[#6d6d6d] text-left items-center sm:items-stretch"
				style="font-weight: 500; line-height: 1.6rem;"
			>
				We genuinely stitch your challenges, and our <span class="text-[#e2e2e2]"
					>fabric <br /> awareness</span
				>
				helps us <span class="text-[#e2e2e2]">weave</span> and
				<span class="text-[#e2e2e2]">craft</span>
				tailored <br />solutions you need, shaping your success,
				<span class="text-[#e2e2e2]">making it <br /> fit!</span>
			</div>
		</div>
	{/if}
</div>

<style>
	.hero-image {
		position: relative;
	}

	.hero-text {
		color: #e2e2e2;
		font-weight: 700;
		width: 14rem;
		line-height: 2rem;
	}

	.hero-text .fashion {
		color: #cb0f0f;
	}

	.hero-image > .image {
		background-image: url(hero.jpg);
		background-position: top;
		background-size: cover;
		height: 15rem;
	}

	.main-text {
		padding: 8rem 16rem;
	}

	@media only screen and (max-width: 850px) {
		.main-text {
			padding: 3rem 12rem;
		}
	}

	@media only screen and (max-width: 600px) {
		.scroll-down {
			display: none;
		}

		.main-text {
			padding: 1rem 4rem;
		}
	}
</style>
