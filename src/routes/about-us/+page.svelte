<script>
	import Tag from '$lib/components/atoms/tag.svelte';
	import Item from '$lib/components/atoms/item.svelte';
    import Intro from '$lib/components/atoms/intro.svelte';
    import IndustryExcellence from '$lib/components/atoms/industry-excellence.svelte';
    import Testimonials from '$lib/components/testimonials.svelte';
    import Location from '$lib/components/location.svelte';

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

    const values = [
        { 
            index: '01',
            title: 'Transparency',
            details: 'We believe in fostering trust through open and clear communication between buyers and suppliers.',
            color: 'white',
        },
        { 
            index: '02',
            title: 'Efficiency',
            details: 'Our goal is to simplify and expedite the procurement process, saving time and reducing costs for our clients.',
            color: 'white',
        },
        { 
            index: '03',
            title: 'Innovation',
            details: 'We are committed to continuously improving our platform and services to meet the evolving needs of the industry.',
            color: 'white',
        },
        { 
            index: '04',
            title: 'Empowerment',
            details: 'We strive to empower businesses by providing the tools and resources they need to succeed and grow.',
            color: 'white',
        },
        { 
            index: '05',
            title: 'Collaboration',
            details: 'We value partnerships and believe in working together with our clients and suppliers to achieve mutual success.',
            color: 'white',
        },
        { 
            index: '06',
            title: 'Integrity',
            details: 'We uphold the highest standards of ethics and professionalism in all our dealings.',
            color: 'white',
        },
    ]

</script>

<div use:actionWhenInViewport class="container sm:items-stretch p-16">
	<Tag text="WE ARE A TEXTILE INDUSTRY" />
	{#if animate}
	<h1
		transition:scale={{ duration: 500, start: 0.5 }}
		class="text-white font-extrabold text-5xl lg:pl-[12rem] md:pl-32 pl-8"
		style="line-height: 2.75rem;"
	>
		Pushing the <br> modern appeal
	</h1>
    <div class="image lg:p-16 md:p-8 p-4 flex justify-center">
        <img src="hero.jpg" alt="hero">
    </div>
	{/if}

    <Tag text="About us" />
	<h1
		class="text-white font-normal text-3xl lg:pl-[16rem] md:pl-32 pl-2 lg:pr-[16rem] md:pr-32 pr-2"
		style="line-height: 1.75rem;"
	>
    A team of international fashion experts comprising stylists, and production specialists. Blending experienced professionals and young talent, fully immersed in the fashion world. This diversity encourages growth through active innovation and craftsmanship.
	</h1>
	


    <div class="flex justify-center lg:gap-36 md:gap-8 gap-4 mb-32">
        <Item item={
            { 
                index: '',
                title: 'Mission',
                details: 'We are committed to offering clothing brands worldwide the highest quality products at fair prices, ensuring total customer satisfaction.',
                color: 'white',
                detailGrey: true
            }
        } />
         <Item item={
            { 
                index: '',
                title: 'Vision',
                details: 'To become the foremost textile and fashion manufacturer of the 21st century, driving the global adoption of the Fourth Industrial Revolution.',
                color: 'white',
                detailGrey: true
            }
        } />
    </div>

    <div>
        <Tag text="Core values" />
	
	<div 
        class="flex flex-wrap justify-center lg:gap-x-36 md:gap-x-8 gap-x-2 mb-32">
        {#each values as value}
         <div  transition:fade={{ duration: 1000 }} class="lg:pl-32 lg:pr-32 md:pl-16 md:pr-16 pl-4 pr-4">
            <Item item={
                value
            } />
         </div>
        {/each}
    </div>


    <Intro />
	
	
    </div>

</div>

<div class="container-white sm:items-stretch p-16">

    <h1 class="font-extrabold text-5xl lg:pl-52 md:pl-32 pl-8 text-[#cb0f0f] ">
        Excellence in <br> every stitch
    </h1>


<div class="lg:grid flex flex-col justify-center grid-cols-6 grid-rows-9 gap-4 p-16">
    <div class="col-span-2 row-span-3 col-start-2 row-start-2">
        <div class="image" style="text-align: -webkit-center;">
            <img style="width: 26rem;" src="hero.jpg" alt="hero">
            <p class="text-[#6d6d6d] text-center text-2xl">years of sustainable business in Pakistan</p>
        </div>
    </div>
<div class="col-span-2 row-span-3 col-start-1 row-start-6">
    <div class="image" style="text-align: -webkit-center;">
        <img style="width: 26rem;" src="hero.jpg" alt="hero">
        <p class="text-[#6d6d6d] text-center text-2xl">years of sustainable business in Pakistan</p>
    </div>
</div>
<div class="col-span-2 row-span-4 col-start-5 row-start-1">
    <div class="image" style="text-align: -webkit-center;">
        <img style="width: 18rem; height: 22rem;" src="hero.jpg" alt="hero">
        <p class="text-[#6d6d6d] text-center text-2xl">years of sustainable business in Pakistan</p>
    </div>
</div>
<div class="col-span-2 row-span-4 col-start-4 row-start-6">
    <div class="image" style="text-align: -webkit-center;">
        <img style="width: 18rem; height: 22rem;" src="hero.jpg" alt="hero">
        <p class="text-[#6d6d6d] text-center text-2xl">years of sustainable business in Pakistan</p>
    </div>
</div>

</div>



</div>

<div class="container sm:items-stretch p-16">
    <IndustryExcellence />

    <Tag text="What our clients say" />
	<h1
		class="text-white font-semibold text-3xl lg:pl-[16rem] md:pl-32 pl-2 lg:pr-[16rem] md:pr-32 pr-2"
		style="line-height: 1.75rem;"
	> 
    We’ve worked with lovely clients from all <br>over the word
    </h1>

    <Testimonials />

    <div class="flex flex-wrap justify-around gap-8 p-16 logos">
        <img src="brands/1.png" alt="OSTIN">
        <img src="brands/2.png" alt="Chaleur 2000">
        <img src="brands/3.png" alt="PETAR PETROV">
    </div>

    <Location/>

</div>

<style>
    .logos {
        align-items: center;
    }
    .logos img {
        height: fit-content;
        width: 12rem;
        transition: all 0.3s ease;
        cursor: pointer;
    }

    .logos img:hover {
        filter: brightness(500%);
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
