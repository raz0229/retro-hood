<script>
	import Tag from './atoms/tag.svelte';
	import Curve from '$lib/svgs/curve.svelte';
	import GridTile from './atoms/grid-tile.svelte';

    let gridTiles = [
        {
            image: 'tiles/tile.jpg',
            index: 1,
            title: 'Trusted Partner',
            subtitle: 'Quality Products',
            details: 'Say goodbye to low-quality manufacturers and hello to guaranteed perfection.'
        },
        {
            image: 'tiles/tile.jpg',
            index: 2,
            title: 'Transform your brand',
            subtitle: 'Failure to Success',
            details: 'Achieve five-figure revenues in just three months, with our expert guidance and support system.'
        },
        {
            image: 'tiles/tile.jpg',
            index: 3,
            title: 'Minimum Order Quantity',
            subtitle: 'Little batches, little perks',
            details: 'We are making a minimum of 30 pieces per color and design.'
        },
        {
            image: 'tiles/tile.jpg',
            index: 4,
            title: 'Expertise You Can Trust',
            subtitle: 'crafting your success',
            details: 'Top-notch quality products that reflect your brand\'s high standards.'
        },
    ]

    function redirectToServicesOnClick (e) {
        e.addEventListener('click', () => {
            location.href = '/about-us'
        })
    }

</script>

<Curve />
<div class="items-center sm:items-stretch p-16">
	<Tag text="Why us" />
	<div class="relative lg:text-5xl md:text-4xl text-2xl title text-white">
		Shaping the <br /> future of Fashion Era
	</div>
	<p class="relative lg:text-2xl md:text-xl text-lg title text-semibold text-[#6d6d6d]">
		with every thread, we bring <br /> your vision to life in fashion <br /> that people will love.
	</p>

	

	<div class="grid-container grid grid-cols-11 grid-rows-12 gap-0">
		
		<div
            use:redirectToServicesOnClick
            class="col-span-2 row-span-4 col-start-4 row-start-1">
            <GridTile
                image="{gridTiles[0].image}"
                index="{gridTiles[0].index}"
                title="{gridTiles[0].title}"
                subtitle="{gridTiles[0].subtitle}"
                details="{gridTiles[0].details}"
            />
        </div>
        <div
            use:redirectToServicesOnClick 
            class="col-span-2 row-span-4 col-start-8 row-start-3">
            <GridTile
                image="{gridTiles[1].image}"
                index="{gridTiles[1].index}"
                title="{gridTiles[1].title}"
                subtitle="{gridTiles[1].subtitle}"
                details="{gridTiles[1].details}"
            />
        </div>
        <div
            use:redirectToServicesOnClick 
            class="col-span-2 row-span-4 col-start-3 row-start-7">
            <GridTile
                image="{gridTiles[2].image}"
                index="{gridTiles[2].index}"
                title="{gridTiles[2].title}"
                subtitle="{gridTiles[2].subtitle}"
                details="{gridTiles[2].details}"
            />
        </div>
		<div
            use:redirectToServicesOnClick 
            class="col-span-2 row-span-4 col-start-7 row-start-9">
            <GridTile
                image="{gridTiles[3].image}"
                index="{gridTiles[3].index}"
                title="{gridTiles[3].title}"
                subtitle="{gridTiles[3].subtitle}"
                details="{gridTiles[3].details}"
            />
        </div>
	</div>
</div>

<style>
	.title {
		margin: 2rem 16rem;
		font-weight: 600;
		z-index: 9;
	}

    @media only screen and (max-width: 950px) {
		.grid-container {
            display: flex;
            flex-wrap: wrap;
            gap: 5rem;
            justify-content: center;
        }
	}

    @media only screen and (max-width: 850px) {
        .title {
            margin: 1rem 6rem;
            line-height: 1.5rem;
        }
    }

    @media only screen and (max-width: 600px) {
        .title {
            margin: 0rem 3rem;
            line-height: 1.5rem;
        }
    }

	
</style>
