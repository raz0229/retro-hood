<script>

    let showMobileMenu = false;
    import { slide } from "svelte/transition";

	let navs = [
		{
			text: 'About us',
			href: '/about-us'
		},
		{
			text: 'Services',
			href: '/services'
		},
		{
			text: 'Products',
			href: '/products'
		},
		{
			text: 'Process',
			href: '/process'
		},
		{
			text: 'Contact us',
			href: '/contact-us'
		}
	];
</script>

<nav class="bg-[#0a0909] pt-6">
	<div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
		<div class="relative flex h-16 items-center justify-between">
			<div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
				<!-- Mobile menu button-->
				<button
                    on:click={()=>showMobileMenu=!showMobileMenu}
					type="button"
					class="relative inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
					aria-controls="mobile-menu"
					aria-expanded="false"
				>
					<span class="absolute -inset-0.5"></span>
					<span class="sr-only">Open main menu</span>
					<!--
              Icon when menu is closed.
  
              Menu open: "hidden", Menu closed: "block"
            -->
					<svg
						class="block h-6 w-6"
						fill="none"
						viewBox="0 0 24 24"
						stroke-width="1.5"
						stroke="currentColor"
						aria-hidden="true"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
						/>
					</svg>
					<!--
              Icon when menu is open.
  
              Menu open: "block", Menu closed: "hidden"
            -->
					<svg
						class="hidden h-6 w-6"
						fill="none"
						viewBox="0 0 24 24"
						stroke-width="1.5"
						stroke="currentColor"
						aria-hidden="true"
					>
						<path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
					</svg>
				</button>
			</div>
			<div
				class="flex flex-1 items-center justify-around sm:items-stretch sm:justify-around"
				style="align-items: center;"
			>
				<div on:click={()=>location.href='/'} class="cursor-pointer flex flex-shrink-0 items-center">
					<img class="h-40 w-auto" src="logo.png" alt="Your Company" />
				</div>
				<div class="hidden sm:ml-6 sm:block">
					<div class="flex space-x-4">
						<!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->

						{#each navs as nav}
							<a
								href={nav.href}
								class="px-3 pt-2 mb-0 text-sm font-medium text-gray-300 hover:border-b-2 hover:border-solid hover:border-sky-500"
								>{nav.text}</a
							>
						{/each}
					</div>
				</div>
			</div>

		</div>
	</div>
    
</nav>

{#if showMobileMenu}
<!-- Mobile menu, show/hide based on menu state. -->
<div in:slide out:slide class="bg-[#0a0909]" style="align-items: center;">
    <div class="sm:ml-6 sm:block">
        <div class="mobile-menu">
            <!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->

            {#each navs as nav}
                <a
                    href={nav.href}
                    class="p-2 pt-2 mb-0 text-sm font-medium text-gray-300 hover:border-b-2 hover:border-solid hover:border-sky-500"
                    >{nav.text}</a
                >
            {/each}
        </div>
    </div>
</div>
{/if}

<style>
	a {
		font-weight: 400;
	}

    .mobile-menu {
        display: grid;
        place-content: center;
        padding: 1rem;
        padding-top: 2rem;
    }

	.underline {
	}
</style>
