<script>
	import Tag from './atoms/tag.svelte';
	import Service from './atoms/service.svelte';
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

	export let services = [
		{
			name: 'Manufacturing',
			image: 'services/manufacturing.jpg',
			details:
				"From the start of your project, you'll have a dedicated Client Account Manager ensuring a smooth transition through every stage—initial concept, sampling, development, and ultimately production. Our expert teams - client managers, developers, and merchandising specialists - respond swiftly to your needs. We deliver innovative solutions through continuous research and testing, prioritizing sustainability."
		}
	];
</script>

<div use:actionWhenInViewport class="sm:items-stretch p-16">
	<Tag text="Services" />

	{#if animate}
		<div transition:scale={{ delay: 300, duration: 500, start: 0.5 }} class="draw">
			{#each services as service}
				<Service serviceName={service.name} details={service.details} />
			{/each}
		</div>
	{/if}
</div>
