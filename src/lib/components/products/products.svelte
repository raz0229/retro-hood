<script>
    import { onMount } from "svelte";
    import { fade, blur } from "svelte/transition";

    let selectedCategory = 'All';
    let tempProducts = [];

	let buttons = [
		{
			text: 'All',
			filter: 'all'
		},
		{
			text: 'Hoodies',
			filter: 'hoodie'
		},
		{
			text: 'Sweatshirts',
			filter: 'sweatshirt'
		},
		{
			text: 'Beanies',
			filter: 'beanie'
		}
	];

    export let products = [
        {
            name: 'Basic Hoodie',
            subtitle: 'Retrohood | Oversized',
            image: 'lineup/hoodie.png',
            type: 'hoodie',
            sizes: ['S', 'M', 'L'],
            selectedSize: 'S',
            price: '20'
        }
    ]

    const selectCategory = (btn) => {
        selectedCategory = btn.text;
		console.log(selectedCategory, btn)
		console.log(selectedCategory == btn.text)
		buttons = buttons

        if (btn.filter == 'all')
            products = tempProducts
        else
            products = tempProducts.filter(product => product.type == btn.filter)
        
    }

    onMount(() => {
        tempProducts = products;
    })

</script>

<div class="lg:p-32 md:p-16 p-2">
	<div class="buttons flex lg:gap-6 md:gap-4 gap-2 flex-wrap">
		{#each buttons as btn}
			{#if selectedCategory == btn.text}
			<button
				on:click={()=>selectCategory(btn)}
				style="min-width: 6rem; text-align: center; outline: none;"
				class="cursor-pointer mt-2 mb-2 rounded-full pt-1 pb-1 pr-3 pl-3 text-white font-normal text-xl bg-[#cb0f0f]"
				class:selected-btn="{selectCategory == btn.text}"
                >{btn.text}</button
			>
			{:else}
			<button
				on:click={()=>selectCategory(btn)}
				style="min-width: 6rem; text-align: center; outline: none;"
				class="cursor-pointer mt-2 mb-2 rounded-full pt-1 pb-1 pr-3 pl-3 text-black font-normal text-xl bg-white hover:bg-gray-200"
				class:selected-btn="{selectCategory == btn.text}"
                >{btn.text}</button
			>
			{/if}
		{/each}
	</div>


    <div class="flex gap-4 flex-wrap justify-center mt-16">
    {#each products as product}
        
    <div
            in:blur
            out:fade
			style="gap: 2rem; max-width: 19rem;"
			class="bg-white lg:p-6 md:p-6 p-2 rounded-lg shadow-sm flex flex-col items-center"
		>
			<img src="{ product.image }" alt="{ product.name }" class="h-100 w-100 object-contain mb-4" />
			<div class="flex justify-center sm-contain mb-4" style="width: 90%; align-items: end;">
				<div class="text-left">
					<h3 class="lg:text-xl md:text-xl text-md font-light text-left text-[#6d6d6d]">{ product.subtitle }</h3>
                    <h3 class="text-2xl font-semibold text-left text-black">{ product.name }</h3>
                    <div class="buttons flex lg:gap-2 md:gap-2 gap-2 flex-wrap">
                         {#each product.sizes as size}
                         <button
                                on:click={()=>product.selectedSize=size}
                                class:bg-red-600="{size == product.selectedSize}"
                                class:text-white="{size == product.selectedSize}"
                                style="text-align: center; min-width: 2rem; outline: none;"
                                class="cursor-pointer mt-2 mb-2 rounded-full p-1 text-black focus:text-white font-normal lg:text-sm md:text-sm text-xs bg-gray-100 hover:bg-gray-200 focus:bg-[#cb0f0f]"
                                >{ size }</button
                            >
                        {/each}
                        
                    </div>
                    <h3 class="text-2xl font-bold text-left text-[#cb0f0f]">${ product.price }</h3>
                    
				</div>
				<button
					class="mt-4 p-4 bg-white text-black border-2 border-gray-200 rounded-full w-12 h-12 flex items-center justify-center hover:bg-gray-100 transition-all"
				>
					<svg
						class="w-6 h-6"
						fill="none"
						stroke="currentColor"
						viewBox="0 0 24 24"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"
						></path>
					</svg>
				</button>
			</div>
		</div>
        {/each}
    </div>
</div>