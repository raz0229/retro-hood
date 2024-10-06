<script>
    import Tag from "./atoms/tag.svelte";
    import Blog from "./atoms/blog.svelte";


    const blogs = [
        {
            title: 'What are the materials used for manufacturing gym clothes?',
            unixTimeInMS: 1728187652781,
            href: '#',
            image: 'blogs/cover.jpg'
        },
        {
            title: 'What are the materials used for manufacturing gym clothes?',
            unixTimeInMS: 1728187652781,
            href: '#',
            image: 'blogs/cover.jpg'
        },
        {
            title: 'What are the materials used for manufacturing gym clothes?',
            unixTimeInMS: 1728187652781,
            href: '#',
            image: 'blogs/cover.jpg'
        }
    ]

</script>

<div class="sm:items-stretch p-16">
    <Tag text="Blogs" />
    <div class="flex justify-center flex-wrap blogs-container" style="gap: 2rem;">
        {#each blogs as blog}
            <Blog
                title="{blog.title}"
                unixTime={blog.unixTimeInMS}
                href="{blog.href}"
                image="{blog.image}"
            />
        {/each}
    </div>
</div>

<style>
    .blogs-container {
        padding: 0 8rem;
    }
</style>