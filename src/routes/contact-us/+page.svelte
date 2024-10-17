<script>
    import Tag from '$lib/components/atoms/tag.svelte';
    import Location from '$lib/components/location.svelte';
	import { scale } from 'svelte/transition';
    import ActionButton from '$lib/components/atoms/action-button.svelte';
	
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

    const submitHandler = () => {
        console.log('Submit event')
    }
</script>

<svelte:head>
	<title>RetroHood | Contact</title>
</svelte:head>

<div use:actionWhenInViewport class="container sm:items-stretch p-16">
	<Tag text="Get in touch" />
	{#if animate}
		<h1
			transition:scale={{ duration: 500, start: 0.5 }}
			class="text-white font-extrabold text-5xl lg:pl-[12rem] md:pl-32 pl-8"
			style="line-height: 2.75rem;"
		>
			Let us tell your story through visuals
		</h1>
	{/if}

	<Location />

	<div class="image flex justify-center mt-16">
		<img src="support.jpg" alt="support">
	</div>

    <Tag text="Contact us" />
    <div class="lg:flex justify-center gap-6" style="align-items: center;">
		<h1
			class="contact-us-now text-[#cb0f0f] font-bold text-8xl lg:pl-[12rem] md:pl-32 pl-8"
			style="line-height: 4.75rem;"
		>
			CONTACT <br> US <br> NOW
		</h1>
		<form class="form lg:pl-40 lg:pr-40 md:pl-24 md:pr-24 pl-4 pr-4">
			<div style="line-height: 1.75rem;" class="text mb-8 font-bold text-white text-3xl">
				We would love to hear from you <br> even if you just want to say Hi!
			</div>
	
			<div style="line-height: 1.75rem;" class="mt-16 text mb-8 font-light text-[#6d6d6d] text-3xl">
				<input style="width: 100%" class="bg-transparent border-b-2 pb-2 border-[#6d6d6d]" placeholder="NAME" type="text">    
			</div>
	
			<div class="lg:flex md:block block gap-16">
				<div style="line-height: 1.75rem; flex-grow: 1;" class="mt-8 text mb-8 font-light text-[#6d6d6d] text-3xl">
					<input style="width: 100%" class="bg-transparent border-b-2 pb-2 border-[#6d6d6d]" placeholder="EMAIL" type="email">    
				</div>
				<div style="line-height: 1.75rem; flex-grow: 1;" class="mt-8 text mb-8 font-light text-[#6d6d6d] text-3xl">
					<input style="width: 100%" class="bg-transparent border-b-2 pb-2 border-[#6d6d6d]" placeholder="PHONE NUMBER" type="phone">    
				</div>
			</div>
	
			<div style="line-height: 1.75rem;" class="mt-16 text mb-8 font-light text-[#6d6d6d] text-3xl">
				<input style="width: 100%" class="mb-16 bg-transparent border-b-2 pb-2 border-[#6d6d6d]" placeholder="YOUR MESSAGE" type="text">    
			</div>
	
			<div class="btn"
				on:click="{submitHandler}"
			>
				<ActionButton text="Submit" />
			</div>
		</form>
	</div>


</div>

<style>

    input {
        outline: none;
    }
	.container,
	.container-white {
		margin: 0;
		max-width: 100%;
		height: 100%;
	}

	@media only screen and (max-width: 1580px) {
		.contact-us-now {
		display: none;
		}

  }


	.container {
		background-color: #0a0909;
	}

	.container-white {
		background-color: #f8f8f8;
	}
</style>
