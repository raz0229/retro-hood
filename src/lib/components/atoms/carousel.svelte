<script>
    export let images = [
      'lineup/product.jpg',
      'lineup/product.jpg',
      'lineup/product.jpg',
      'lineup/product.jpg',
      'lineup/product.jpg',
      'lineup/product.jpg',
      'lineup/product.jpg',
    ];
  </script>
  
  <div class="overflow-hidden slider relative w-full h-64 m-16">
    <!-- The sliding wrapper -->
    <div class="flex space-x-4 animate-slide whitespace-nowrap">
      {#each images.concat(images) as image}
        <img src={image} class="w-full h-64 object-cover inline-block shadow-inner shadow-xl" alt="Carousel Image" />
      {/each}
    </div>
  </div>
  
  <style>
    @keyframes slide {
      0% {
        transform: translateX(0);
      }
      100% {
        transform: translateX(-100%);
      }
    }

    img {
      width: 15rem;
      height: 15rem;
    }
  
    .animate-slide {
      animation: slide 5s linear infinite;
    }

    @media only screen and (max-width: 600px) {
		.slider {
      margin-left: 0 !important;
    }
  }
  </style>