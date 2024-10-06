<script>
    import Hero from "$lib/components/hero.svelte";
    import Services from "$lib/components/services.svelte";
    import Blogs from "$lib/components/blogs.svelte";
    import Slider from "$lib/components/slider.svelte";
    import Products from "$lib/components/products.svelte";
    import WhyUs from "$lib/components/why-us.svelte";
</script>

<div class="container">
    <Hero />
    <WhyUs />
    <Services />
</div>

<div class="container-white">
    <Products />
    <Slider />
    <Blogs />
</div>



<style>
    .container, .container-white {
        margin: 0;
        max-width: 100%;
        height: 100%;
    }

    .container {
        background-color: #0a0909;
    }

    .container-white {
        background-color: #f8f8f8;
    }
</style>