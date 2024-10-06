<script>

    import { fade } from "svelte/transition";

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

	export let image = 'tiles/tile.jpg';
    export let index = 1;
    export let title = 'Trusted Partner';
    export let subtitle = 'Quality Products';
    export let details = 'Say goodbye to low-quality manufacturers and hello to guaranteed perfection.'
</script>

<div use:actionWhenInViewport class="tile relative">
	{#if animate}
    <div transition:fade={{duration:500, delay: 200}} class="image relative">
        <span class="absolute index">{ index }</span>
		<img src={image} class="shadow-inner object-contain m-4" />
	</div>
    <div transition:fade={{duration:500, delay: 200}} class="title ml-4 text-white font-bold text-2xl">
        { title }
    </div>
    <div transition:fade={{duration:500, delay: 200}} class="subtitle ml-4 font-light text-2xl text-[#6d6d6d]">
        { subtitle }
    </div>
    <div transition:fade={{duration:500, delay: 200}} class="details ml-4 font-light text-xl text-[#6d6d6d]">{ details }</div>
    {/if}
</div>

<style>
    .tile {
        max-width: 18rem;
        cursor: pointer;
    }
    .index {
        -webkit-text-fill-color: transparent;
		-webkit-text-stroke: 2px;
		-webkit-text-stroke-color: #6d6d6d;
		font-weight: 800;  
        font-size: 15rem;
        left: -4rem;
        top: 1rem;
        z-index: 2;
        transition: all 0.5s ease;
    }
    .tile:hover .index {
        -webkit-text-fill-color: #cb0f0f;
        -webkit-text-stroke: 0px;
    }
    img {
        width: 15rem;
        z-index: 9;
        position: relative;
        filter: drop-shadow(0 4px 3px rgba(208, 208, 208, 0.4)) drop-shadow(0 2px 2px rgba(202, 202, 202, 0.4));
    }
    .subtitle {
        text-transform: uppercase;
        margin-top: 1rem;
        margin-bottom: 1rem;
        padding-top: 1rem;
        line-height: 1.4rem;
        border-top: solid 1px #6d6d6d;
    }
    .details {
        line-height: 1rem;
    }
    
</style>
