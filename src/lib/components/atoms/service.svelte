<script>
	export let serviceName = 'My Service';
	export let details = 'lorem ipsum';

	let isHovered = false;
</script>

<div
	on:mouseover={() => (isHovered = true)}
	on:mouseout={() => (isHovered = false)}
	class="service"
>
	<div class:filled={isHovered} class="z-20 hover:filled name text-5xl relative">
		{serviceName}
	</div>
	<div
		class:opacity-full={isHovered}
		class="opacity-0 z-10 absolute ct mt-[-5rem] ml-[-4rem] mr-8 flex"
		style="gap: 2rem; transition: opacity 0.5s ease-in-out;"
	>
		<img src="hero.jpg" alt={serviceName} />
		<div class="details">
			<div class="text-3xl pt-2 pb-2 text-white">
				{serviceName}
			</div>
			<div class="border-t-2 border-t-[#6d6d6d] pt-6 text-[#6d6d6d]">
				<p class="text-xl" style="line-height: 1.3rem;">
					{details}
				</p>
			</div>
		</div>
	</div>
</div>

<style>

    img {
        width: 26rem;
    }

	.service {
		margin: 4rem 16rem;
        cursor: pointer;
	}

	.filled {
		-webkit-text-fill-color: crimson !important;
		-webkit-text-stroke: 0 !important;
	}

	.opacity-full {
		opacity: 100%;
	}

	.service .name {
		-webkit-text-fill-color: transparent;
		-webkit-text-stroke: 0.5px;
		-webkit-text-stroke-color: #ffffff;
		font-weight: 600;
	}

	@media only screen and (max-width: 950px) {
		.service {
			margin: 3rem 12rem;
		}
        img {
            width: 20rem;
            height: 12rem;
        }
        .ct {
            display: none;
        }
	}

	@media only screen and (max-width: 800px) {
		.service {
			margin: 2rem 0rem;
		}
        img {
            width: 15rem;
            height: 10rem;
        }

        .ct {
            display: none;
        }
	}
</style>
