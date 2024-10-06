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
            <h3 class="text-2xl font-light text-left text-[#6d6d6d]">{product.name}</h3>
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
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M9 5l7 7-7 7"
              ></path>
            </svg>
          </button>
    </div>
  </div>