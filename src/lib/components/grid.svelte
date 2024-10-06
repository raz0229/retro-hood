<script>
    import Product from "./atoms/product.svelte";
    import ActionButton from "./atoms/action-button.svelte";
    
    let products = [
      {
        id: 1,
        name: "Basic Black Hoodie Kaius 01 Three",
        image: "/lineup/hoodie.png",
      },
      {
        id: 2,
        name: "Basic Black Hoodie Kaius 01 Three",
        image: "/lineup/hoodie.png",
      },
      {
        id: 3,
        name: "Basic Black Hoodie Kaius 01 Three",
        image: "/lineup/hoodie.png",
      },
      {
        id: 4,
        name: "Basic Black Hoodie Kaius 01 Three",
        image: "/lineup/hoodie.png",
      }
    ];
  </script>
  
  <div class="container mx-auto py-8 relative">
    <!-- Products grid -->
    <!-- <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each products as product}
          <Product product="{product}" />
      {/each}
    </div> -->

    <div class="grid grid-cols-1 md:grid-cols-2 lg:flex gap-8 justify-center items-center">
      <Product product="{products[0]}" />
      <div class="flex gap-8 flex-col">
        <Product product="{products[1]}" />
        <Product product="{products[2]}" />
      </div>
      <Product product="{products[3]}" />
    </div>
  
    <!-- Button at the bottom -->
    <div class="absolute right-2 md:bottom-16 lg:bottom-16">
      <ActionButton text="See all products" />
    </div>
  </div>
  