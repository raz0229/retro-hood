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

	const services = [
		{
			name: 'Manufacturing',
			image: 'services/manufacturing.jpg',
			details:
				"From the start of your project, you'll have a dedicated Client Account Manager ensuring a smooth transition through every stage—initial concept, sampling, development, and ultimately production. Our expert teams - client managers, developers, and merchandising specialists - respond swiftly to your needs. We deliver innovative solutions through continuous research and testing, prioritizing sustainability."
		},
		{
			name: 'Procurement',
			image: 'services/procurement.jpg',
			details:
				'Our extensive procurement division sources diverse fabrics globally, offering everything from basic single jersey to high-quality 500 gsm loopback cotton and terry fleece. We partner with suppliers across Pakistan to guarantee quality and environmental commitment, offering organic cotton, viscose, poly, and various blends.'
		},
		{
			name: 'Printing',
			image: 'services/printing.jpg',
			details:
				'Our state-of-the-art printing factory employs various techniques, including heat-sensitive printing, heat transfer, and digital printing on advanced TAS machines. With cutting-edge equipment, we ensure a high-quality product with a monthly output of 10,000 – 13,000 panels.'
		},
		{
			name: 'Treatment',
			image: 'services/treatment.jpg',
			details:
				'Our in-house Tajima embroidery machines, stone application, heat transfers, and other specialist equipment ensure premium quality.We also collaborate with trusted vendors for unique finishes like tie-dyeing and marble washing, using eco-friendly, water-based inks.'
		},
		{
			name: 'Sewing',
			image: 'services/sewing.jpg',
			details:
				'With 10 dedicated full-time operators across seven lines, our daily output can reach 100 units. Our team, skilled in using 3-5 different machine types, ensures diverse, high-quality products with minimal downtime.'
		},
		{
			name: 'Warehousing',
			image: 'services/warehousing.jpg',
			details:
				'We provide comprehensive storage and warehouse solutions, managing individual store packing, direct dispatch, and specialized processing for department stores. Our ERP system ensures transparency and efficiency in managing goods movement and storage.'
		},
		{
			name: 'Quality Control',
			image: 'services/quality-control.jpg',
			details:
				'Adhering to international AQL 2.5 standards, we conduct AQL 1.5 final inspections and additional internal QC checkpoints at each production stage. Our testing facility ensures every garment meets durability, colorfastness, tear strength, weight, fabric twist, and shrinkage standards'
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
