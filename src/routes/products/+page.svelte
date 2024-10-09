<script>
    import Tag from '$lib/components/atoms/tag.svelte';
    import Products from '$lib/components/products/products.svelte';

    import { fade, scale } from 'svelte/transition';
	
	let animate = false;

    let products = [
        {
            name: 'White Hoodie',
            subtitle: 'Retrohood | Oversized',
            type: 'hoodie',
            image: 'lineup/hoodie-white.png',
            sizes: ['S', 'M', 'L'],
            selectedSize: 'S',
            price: '20'
        },
        {
            name: 'Basic Hoodie',
            subtitle: 'Retrohood | Hoodie',
            type: 'hoodie',
            image: 'lineup/hoodie.png',
            sizes: ['S', 'M', 'L'],
            selectedSize: 'S',
            price: '10'
        },
        {
            name: 'Basic Hoodie',
            subtitle: 'Retrohood | Sweatshirt',
            type: 'sweatshirt',
            image: 'lineup/hoodie.png',
            sizes: ['S', 'M', 'L'],
            selectedSize: 'S',
            price: '45'
        },
        {
            name: 'Basic Jacket',
            subtitle: 'Retrohood | Hoodie',
            type: 'hoodie',
            image: 'lineup/hoodie-white.png',
            sizes: ['S', 'M', 'L'],
            selectedSize: 'S',
            price: '20'
        },
        {
            name: 'Basic Hoodie',
            subtitle: 'Retrohood | Hoodie',
            type: 'hoodie',
            image: 'lineup/hoodie.png',
            sizes: ['S', 'M', 'L'],
            selectedSize: 'S',
            price: '15'
        },
        {
            name: 'Basic Hoodie',
            subtitle: 'Retrohood | Sweatshirt',
            type: 'sweatshirt',
            image: 'lineup/hoodie.png',
            sizes: ['S', 'M', 'L'],
            selectedSize: 'S',
            price: '19.99'
        },
        {
            name: 'Basic Hoodie',
            subtitle: 'Retrohood | Beanie',
            type: 'beanie',
            image: 'lineup/hoodie.png',
            sizes: ['S', 'M', 'L'],
            selectedSize: 'S',
            price: '5'
        },
    ]

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

<div use:actionWhenInViewport class="container sm:items-stretch p-16">
	<Tag text="How we do it" />
	{#if animate}
	<h1
		transition:scale={{ duration: 500, start: 0.5 }}
		class="text-white font-extrabold text-5xl lg:pl-[12rem] md:pl-32 pl-8"
		style="line-height: 2.75rem;"
	>
		Fashion <br> that speaks <br> volume.
	</h1>
	{/if}
</div>

<div class="container-white sm:items-stretch p-16">
    <Tag text="Products" />
	<h1
		transition:scale={{ duration: 500, start: 0.5 }}
		class="text-black font-bold text-3xl lg:pl-[12rem] md:pl-32 pl-8"
		style="line-height: 1.75rem;"
	>
		Explore our collection <br> and experience the art of style
	</h1>
    
    <Products 
        products="{products}"
    />

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