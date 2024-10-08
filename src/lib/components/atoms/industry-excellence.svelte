<script>
	import Tag from '$lib/components/atoms/tag.svelte';
	import Count from '$lib/components/atoms/count.svelte';

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

<Tag text="Industry Excellence" />

<div
    use:actionWhenInViewport
    class="flex flex-wrap justify-center">
	{#if animate}
    <div transition:scale={{ start: 0.5, duration: 800, delay: 300 }}>
		<Count number="75" text="years of sustainable business in Pakistan" />
		<Count number="#1" text="Employer of choice from past 13 years" />
		
	</div>
	<div transition:scale={{ start: 0.5, duration: 800, delay: 300 }}>
        <Count number="30+" text="brands in our market" />
		<Count number="90%" text="in Pakistani household" />
	</div>
    {/if}
</div>
