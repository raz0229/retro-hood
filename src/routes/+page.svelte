<script>
    import Hero from "$lib/components/hero.svelte";
    import Services from "$lib/components/services.svelte";
    import Blogs from "$lib/components/blogs.svelte";
</script>

<div class="container">
    <Hero/>
    <Services/>
</div>

<Blogs />


<style>
    .container {
        margin: 0;
        background-color: #0a0909;
        max-width: 100%;
        height: 100%;
    }
</style>