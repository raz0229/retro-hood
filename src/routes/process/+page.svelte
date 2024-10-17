<script>
	import Tag from '$lib/components/atoms/tag.svelte';
	import Item from '$lib/components/atoms/item.svelte';

	import { fade, scale } from 'svelte/transition';

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

	let processes = [
		{
			index: '01',
			title: 'Fabric Selection',
			backgroundColor: '#cb0f0f',
			indexColor: 'white',
			padding: 16,
			width: 100,
			image: '/process/1.jpg',
			details:
				'Your dedicated representative will initially help you select the best fabric for your product.'
		},
		{
			index: '02',
			title: 'Cutting & Sewing',
			backgroundColor: '#cb0f0f',
			indexColor: 'white',
			padding: 16,
			width: 100,
			image: '/process/2.jpg',
			details:
				'Once the fabric is selected, it is sent for Cut & Sew processes to make sure that the quality of the product is not compromised at all.'
		},
		{
			index: '03',
			title: 'Customization',
			backgroundColor: '#cb0f0f',
			indexColor: 'white',
			padding: 16,
			width: 100,
			image: '/process/3.jpg',
			details:
				'At this step, all the changes you need in terms of printing, add-ons and changes are done effectively.'
		},
		{
			index: '04',
			title: 'Labelling',
			backgroundColor: '#cb0f0f',
			indexColor: 'white',
			padding: 16,
			width: 100,
			image: '/process/4.jpg',
			details:
				'Once your product is finalized, we make sure that every piece has your label before it is sent to the packaging department.'
		},
		{
			index: '05',
			title: 'Packaging',
			backgroundColor: '#cb0f0f',
			indexColor: 'white',
			padding: 16,
			width: 100,
			image: '/process/5.jpg',
			details:
				'The final product is ironed, folded with care and packed in the baggage of your choice to give it a premium look.'
		},
		{
			index: '06',
			title: 'Shipment',
			backgroundColor: '#cb0f0f',
			indexColor: 'white',
			padding: 16,
			width: 100,
			image: '/process/6.jpg',
			details:
				'Once the order is packed and ready, it is sent for shipment to your location with minimum shipping time.'
		}
	];

    let models = [
        {
            index: '01',
            title: 'Quality',
            details: 'More like an ad hoc approach, we provide support based on your need for the day and bill based on the time spent. No strings attached, or yes!?!',
            color: 'white'
        },
        {
            index: '02',
            title: 'Quality',
            details: 'More like an ad hoc approach, we provide support based on your need for the day and bill based on the time spent. No strings attached, or yes!?!',
            color: 'white'
        },
        {
            index: '03',
            title: 'Quality',
            details: 'More like an ad hoc approach, we provide support based on your need for the day and bill based on the time spent. No strings attached, or yes!?!',
            color: 'white'
        },
        {
            index: '04',
            title: 'Quality',
            details: 'More like an ad hoc approach, we provide support based on your need for the day and bill based on the time spent. No strings attached, or yes!?!',
            color: 'white'
        },
    ]
    

</script>

<svelte:head>
    <title>RetroHood | Process</title>
</svelte:head>

<div use:actionWhenInViewport class="container sm:items-stretch p-16">
	<Tag text="HOW WE DO IT" />
	{#if animate}
	<h1
		transition:scale={{ duration: 500, start: 0.5 }}
		class="text-white font-extrabold text-5xl lg:pl-[12rem] md:pl-32 pl-8"
		style="line-height: 2.75rem;"
	>
		Everything starts <br /> with conveying <br /> with the users
	</h1>
	{/if}

	<Tag text="Ideology" />
	{#if animate}
	<h1
		transition:scale={{ duration: 500, start: 0.5 }}
		class="text-[#6d6d6d] font-normal text-3xl lg:pl-[12rem] md:pl-32 pl-8"
		style="line-height: 1.75rem;"
	>
		Being a <span class="text-[#cb0f0f]">user-centric business for businesses/brands</span>,<br />
		we make it happen for you through quality and ease of <br />use. Here is the path we follow
		secretly.
	</h1>
	{/if}
</div>

<div 
	class="container sm:items-stretch lg:p-16 md:p-8 p-2">
	<Tag text="Process" />
	<div class="flex justify-between lg:p-16 md:p-8 p-8">
		<div>
			<h1
				class="text-white font-medium lg:text-5xl md:text-5xl text-3xl lg:pl-[12rem] md:pl-32 pl-2"
				style="line-height: 2.75rem;"
			>
				Quality is Everything
			</h1>
			<h1
				class="text-white mt-4 font-light text-2xl lg:pl-[12rem] md:pl-32 pl-2"
				style="line-height: 1.25rem;"
			>
				May it be about yourself or others, We <br />
				apply this in whatever we do. <br />
				The path:
			</h1>
		</div>
		<div
			style="max-width: 8rem;"
			class="lg:block md:hidden hidden image lg:p-12 md:p-8 p-2 lg:mr-[12rem] md:mr-32 mr-2 bg-red-700 rounded-full"
		>
			<img style="width: 2rem; rotate: -180deg; " src="arrow-slanted-white.png" alt="" />
		</div>
	</div>


	{#each processes as process, i}
	<div style="align-items: end;" class="flex lg:flex-row md:flex-col flex-col justify-between lg:gap-24 md:gap-16 gap-4 lg:mr-64 lg:ml-64 md:mr-16 md:ml-16 mr-4 ml-4">
		{#if i%2==0}
		<div class="flex-1"><Item item={process} /></div>
		<div class="image flex-1">
			<img style="width: 40rem;" src="{process.image}" alt="/hero.jpg">
		</div>
		{:else}
		<div class="image flex-1">
			<img style="width: 40rem;" src="{process.image}" alt="/hero.jpg">
		</div>
		<div class="flex-1"><Item item={process} /></div>
		
		{/if}
	</div>
	{/each}
	
		

	
</div>

<div
	use:actionWhenInViewport
	class="container sm:items-stretch p-16">
	<Tag text="Model" />
	
    <div>
        <h1
            class="text-white font-medium lg:text-5xl md:text-5xl text-3xl lg:pl-[12rem] md:pl-32 pl-2"
            style="line-height: 2.75rem;"
        >
            Getting things done to <br> your needs
        </h1>
        
    </div>
	<div
		class="lg:grid lg:pl-42 lg:pr-42 md:flex md:flex-wrap block lg:grid-cols-12 lg:grid-rows-12 gap-4"
	>
		{#if animate}
		<div transition:fade={{ delay: 300, duration: 900 }} class="col-span-3 row-span-3 col-start-3"><Item item={models[0]} /></div>
		<div transition:fade={{ delay: 300, duration: 900  }} class="col-span-3 row-span-3 col-start-8 row-start-2"><Item item={models[1]} /></div>
		<div transition:fade={{ delay: 300, duration: 900 }} class="col-span-3 row-span-3 col-start-3 row-start-5"><Item item={models[2]} /></div>
		<div transition:fade={{ delay: 300, duration: 900  }} class="col-span-3 row-span-3 col-start-8 row-start-6"><Item item={models[3]} /></div>
		{/if}
	</div>
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
