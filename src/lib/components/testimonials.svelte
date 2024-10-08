<script>
	import { fly } from 'svelte/transition';
	import { quintInOut } from 'svelte/easing';

	let animate = true;

	const testimonials = [
		{
			name: 'Siraj Khan',
			image: 'testimonial.png',
			designation: 'Co-founder outfitters',
			location: 'Karachi, Pakistan',
			review:
				'Their attention to detail and commitment to quality make every piece a statement of style. A brand that defines elegance.'
		},
		{
			name: 'Nadir Khan',
			image: 'testimonial.png',
			designation: 'Co-founder outfitters',
			location: 'Karachi, Pakistan',
			review:
				'Their attention to detail and commitment to quality make every piece a statement of style. A brand that defines elegance.'
		},
		{
			name: 'Amir Gujjar',
			image: 'testimonial.png',
			designation: 'Co-founder outfitters',
			location: 'Karachi, Pakistan',
			review:
				'Their attention to detail and commitment to quality make every piece a statement of style. A brand that defines elegance.'
		}
	];

	let currentIndex = 0;

	const moveRight = () => {
		
			animate = false;
			currentIndex = currentIndex == testimonials.length - 1 ? currentIndex : currentIndex + 1;

			setTimeout(() => {
				animate = true;
			}, 300);
		
	};

	const moveLeft = () => {
		
			animate = false;
			currentIndex = currentIndex == 0 ? currentIndex : currentIndex - 1;

			setTimeout(() => {
				animate = true;
			}, 300);
		
	};
</script>

{#if animate}
	<div
		in:fly={{ duration: 300, x: 600, opacity: 0.5 }}
		out:fly={{ duration: 300, x: -600, opacity: 0.5 }}
		class="lg:p-32 md:p-16 p-4"
	>
		<h3 class="font-normal text-3xl text-white">0{currentIndex + 1}/03</h3>

		<h3
			class="lg:flex md:flex block justify-between font-bold text-2xl pt-4 pb-4 text-white lg:ml-16 md:ml-8 ml-2"
			style="line-height: 1.6rem;"
		>
			<div>
				<span class="text-[#cb0f0f]">Retrohood</span> consistently delivers <br /> beyond expectations.
			</div>
			<div class="flex gap-2 mb-8 mt-8">
				<div
					on:click={moveLeft}
					style="transition: all 0.3s ease; width: 5rem; height: 5rem; display: grid; place-content: center;"
					class="cursor-pointer hover:bg-[#cb0f0f] rounded-full border-2 border-[#cb0f0f] arrow-left"
				>
                    {#if currentIndex == 0}
					<img
						class=" p-6"
						src="arrow-left-disabled.png"
						alt="left"
					/>
                    {:else}
                    <img
						class=" p-6"
						src="arrow-left.png"
						alt="left"
					/>
                    {/if}
				</div>

				<div
					on:click={moveRight}
					style="transition: all 0.3s ease; width: 5rem; height: 5rem; display: grid; place-content: center;"
					class="cursor-pointer hover:bg-[#cb0f0f] rounded-full border-2 border-[#cb0f0f] arrow-left"
				>
                    {#if currentIndex == testimonials.length - 1}
					<img
						class=" p-6"
						src="arrow-right-disabled.png"
						alt="right"
					/>
                    {:else}
                    <img
						class=" p-6"
						src="arrow-right.png"
						alt="right"
					/>
                    {/if}
				</div>
			</div>
		</h3>

		<div class="testimonial lg:mr-32 lg:ml-32 md:mr-16 md:ml-16 ml-0 mr-0">
			<div class="flex justify-end">
				<h4
					style="max-width: 31rem;"
					class="lg:text-3xl md:text-3xl text-2xl font-light text-white"
				>
					{testimonials[0].review}
				</h4>
			</div>
			<div class="flex flex-wrap gap-12 justify-center mt-8 mb-8">
				<div class="image">
					<img style="width: 6rem;" src="testimonial.png" alt="profile" />
				</div>
				<div class="lg:text-left md:text-left text-center">
					<h3 class="mt-2 mb-2 text-3xl font-bold text-white">{testimonials[currentIndex].name}</h3>
					<h3 style="text-transform: uppercase;" class="mt-2 text-2xl font-light text-white">
						{testimonials[currentIndex].designation}
					</h3>
					<h3 class="mb-2 mt-[-4px] text-2xl font-light text-[#6d6d6d]">
						{testimonials[currentIndex].location}
					</h3>
				</div>
			</div>
		</div>
	</div>
{/if}
