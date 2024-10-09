<script>
    import Tag from '$lib/components/atoms/tag.svelte';
	import { scale } from 'svelte/transition';
	
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

<svelte:head>
	<title>RetroHood | Contact</title>
</svelte:head>

<div use:actionWhenInViewport class="container sm:items-stretch p-16">
	<Tag text="Get in touch" />
	{#if animate}
		<h1
			transition:scale={{ duration: 500, start: 0.5 }}
			class="text-white font-extrabold text-5xl lg:pl-[12rem] md:pl-32 pl-8"
			style="line-height: 2.75rem;"
		>
			Let us tell your story through visuals
		</h1>
	{/if}
</div>

<style>
	.container,
	.container-white {
		margin: 0;
		max-width: 100%;
		height: 100%;
	}

	.container {
		background-color: #0a0909;
	}

	.container-white {
		background-color: #f8f8f8;
	}
</style>
