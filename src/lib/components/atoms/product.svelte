<script>
    export let product;
</script>

<div 
style="gap: 2rem; min-width: 19rem;"
class="bg-white p-6 rounded-lg shadow-sm flex flex-col items-center">
    <img
      src={product.image}
      alt={product.name}
      class="h-100 w-100 object-contain mb-4"
    />
    <div class="flex justify-center sm-contain" style="width: 90%;">
        <div class="text-center">
            <h3 class="text-2xl font-normal text-left text-[#6d6d6d]">{product.name}</h3>
          </div>
          <!-- <button
            class="mt-4 p-4 bg-white text-black border-2 border-gray-200 rounded-full w-12 h-12 flex items-center justify-center hover:bg-gray-100 transition-all"
          >
          <svg id='Menu_24' class="w-6 h-6" viewBox='0 0 24 24' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'><rect width='24' height='24' stroke='none' fill='#000000' opacity='0'/>


            <g transform="matrix(0.4 0 0 0.4 12 12)" >
            <path style="stroke: none; stroke-width: 1; stroke-dasharray: none; stroke-linecap: butt; stroke-dashoffset: 0; stroke-linejoin: miter; stroke-miterlimit: 4; fill: rgb(0,0,0); fill-rule: nonzero; opacity: 1;" transform=" translate(-25, -25)" d="M 0 9 L 0 11 L 50 11 L 50 9 Z M 0 24 L 0 26 L 50 26 L 50 24 Z M 0 39 L 0 41 L 50 41 L 50 39 Z" stroke-linecap="round" />
            </g>
            </svg>
          </button> -->
    </div>

    <div class="text-center">
      <h3 class="text-xl font-light text-left text-[#6d6d6d]">Lorem ipsum. Product Description <br> Lorem ipsum. Product Description 2nd line</h3>
    </div>
  </div>