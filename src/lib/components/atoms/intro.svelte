<script>
    import Tag from "./tag.svelte";
    import { slide } from 'svelte/transition';
    import Item from "./item.svelte";

    const items = [
        { 
            index: '',
            title: '',
            details: 'At RetroHood , we are driven by a simple yet powerful mission: to offer clothing brands worldwide the highest quality products at fair prices, ensuring total customer satisfaction. Our journey began with a dream to revolutionize the textile and fashion manufacturing industry, and today, we are proud to be at the forefront of this transformation.',
            color: 'white',
            detailGrey: true
        },
        { 
            index: '',
            title: '',
            details: 'We believe in transparency, innovation, and collaboration. Our seamless process takes you from concept to production, with expert teams delivering sustainable solutions. We source quality fabrics globally and use state-of-the-art equipment for premium results. You can count on secure storage, rigorous quality control, and exceptional garments that meet international standards.',
            color: 'white',
            detailGrey: true
        },
        { 
            index: '',
            title: '',
            details: 'At RetroHood, we are more than just a manufacturer we are a partner in your success. Our commitment to innovation, quality, and customer satisfaction drives everything we do. Join us on this transformative journey of innovation and collaboration. Together, we can build a brighter future, driven by resilience, vision, and a steadfast commitment to excellence.',
            color: 'white',
            detailGrey: true
        },
    ]

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

<div use:actionWhenInViewport class="container sm:items-stretch lg:p-16 md:p-12 p-2">
    <Tag text="Established in 2023" />

    {#if animate}
    <h1
    transition:slide={{ duration: 1000, delay: 300 }}
		class="text-white font-normal text-3xl lg:pl-[16rem] md:pl-32 pl-2 lg:pr-[16rem] md:pr-32 pr-2"
		style="line-height: 1.75rem;"
	>
    Hello, I’m Muhammad Mohid ,the CEO of <span class="text-[#cb0f0f]">Retrohood</span>, and I’d like to share our story.
    </h1>
    {/if}

    <div class="flex flex-wrap lg:gap-20 md:gap-12 gap-2 justify-center">
        {#each items as item}
        <div transition:fade>
            <Item {item} />
        </div>
        {/each}
    </div>

</div>


<style>
    .container {
        border-top: solid 1px #6d6d6d;
    }
</style>