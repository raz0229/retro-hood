<script>
    let galleryItems = [
        {
            image: '/gallery/1.jpg',
            hoverImage: '/brands/levis.png',
        },
        {
            image: '/gallery/2.jpg',
            hoverImage: '/brands/tommy.png',
        },
        {
            image: '/gallery/3.jpg',
            hoverImage: '/brands/zara.png',
        },
        {
            image: '/gallery/4.jpg',
            hoverImage: '/brands/nike.png',
        },
        {
            image: '/gallery/5.jpg',
            hoverImage: '/brands/adidas.png',
        },
        {
            image: '/gallery/6.jpg',
            hoverImage: '/brands/lv.png',
        },
        {
            image: '/gallery/7.jpg',
            hoverImage: '/brands/chanel.png',
        },
        {
            image: '/gallery/8.jpg',
            hoverImage: '/brands/hnm.png',
        },
        {
            image: '/gallery/9.jpg',
            hoverImage: '/brands/versace.png',
        },
    ]
</script>

<div class="container mx-auto py-8">
    <!-- component -->
<section class="text-gray-600 body-font">
    <div class="container px-5 py-24 mx-auto">
      <div class="flex flex-wrap -m-4">
        
        {#each galleryItems as item}
        <div class="lg:w-1/3 sm:w-1/2 p-1">
            <div class="flex relative">
              <img alt="gallery" class="absolute rounded-3xl inset-0 w-full h-full object-cover object-center" src="{ item.image }">
              <div style="height: 26rem; align-content: center; text-align: -webkit-center; text-align: -moz-center; transition: opacity 0.3s ease; cursor: pointer;" class="px-8 py-10 relative z-10 w-full bg-transparent opacity-0 hover:opacity-100">
                <img style="width: 18rem;" alt="gallery" class="inset-0 object-center" src="{ item.hoverImage }">
              </div>
            </div>
          </div>
          
        {/each}

      </div>
    </div>
  </section>
</div>