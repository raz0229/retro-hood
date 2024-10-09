<script>
	import Tag from '$lib/components/atoms/tag.svelte';
	import { fade, scale } from 'svelte/transition';
	import Item from '$lib/components/atoms/item.svelte';
    import Testimonials from '$lib/components/testimonials.svelte';

	let animate = false;

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
				'With 10 dedicated full-time operators across seven lines, our daily output can reach 100 units. Our team, skilled in using 3-5 different machine types, ensures diverse, high-quality products with minimal downtime.',
			subdetails: [
				{
					name: 'Fabric Warehouse',
					details:
						"Maximize your fabric's potential with our 390 square per meter warehouse, storing up to 7,000 fabrics with precision and care."
				},
				{
					name: 'Trims Warehouse',
					details:
						'Streamline your trim storage with our 50 square per meter warehouse, expertly organizing and safeguarding your valuable trim collections.'
				},
				{
					name: 'Finished Goods Warehouse',
					details:
						'Secure and efficient storage for your finished goods in our 100 square per meter warehouse, equivalent to 2 x 40 ft containers.'
				},
				{
					name: 'Overstock and assets warehouse',
					details:
						'Optimize your storage needs with our 20 square per meter overstock and asset warehouse, expertly handling excess inventory and valuable assets.'
				}
			]
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
    <title>RetroHood | Services</title>
</svelte:head>

<div use:actionWhenInViewport class="container sm:items-stretch p-16">
	<Tag text="what we do" />
	{#if animate}
		<h1
			transition:fade={{ duration: 500 }}
			class="text-white font-extrabold text-5xl lg:pl-[12rem] md:pl-32 pl-8"
			style="line-height: 2.75rem;"
		>
			We value our weave, and <br /> have a deep passion <br /> for fashion.
		</h1>
	{/if}

	<Tag text="Services" />
	{#if animate}
		<h1
			transition:fade={{ duration: 500 }}
			class="text-white font-normal text-3xl lg:pl-[12rem] md:pl-32 pl-8"
			style="line-height: 1.75rem;"
		>
			We discover what you need <br /> and create a seamless solution, <br /> from development to delivery
		</h1>
	{/if}

   
    {#each services as service, i}
    
	<div 
    transition:scale={{ duration: 500, start: 0.5 }}
        class="service lg:pl-48 lg:pr-48 md:pl-16 md:pr-0 pl-2 pr-0">
		<h1 class="index mt-24 text-5xl">0{i+1}</h1>
		<h1 class="title text-white mb-4 font-normal text-4xl" style="line-height: 1.75rem;">
			{ service.name }
		</h1>

		<div
			class="image flex flex-col gap-16 justify-center lg:p-12 md:p-6 p-2 border-t-2 border-[#6d6d6d]"
		>
			<img style="width: 45rem;" src="{ service.image }" alt="hero" />

			<h1 class="text-white font-extralight text-2xl" style="line-height: 1.75rem;">
				{ service.details }
			</h1>
		</div>

		<div class="flex flex-wrap justify-center lg:gap-16 md:gap-8 gap-4 mb-32">
			{#if service?.subdetails}
            {#each service.subdetails as subd, j}
            <Item
				item={{
					index: `0${j+1}`,
					title: subd.name,
					details: subd.details,
					color: 'white',
					detailGrey: true
				}}
			/>
            {/each}
            {/if}
			
		</div>
	</div>
    
    {/each}
    
</div>

<div class="container-white sm:items-stretch p-16">
    <Testimonials color="black" />
</div>

<style>
	.index {
		-webkit-text-fill-color: transparent;
		-webkit-text-stroke: 2px;
		-webkit-text-stroke-color: #6d6d6d;
		font-weight: 500;
		font-size: 6rem;
		z-index: 2;
		transition: all 0.5s ease;
	}

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
