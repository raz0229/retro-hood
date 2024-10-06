<script>
	import Tag from './atoms/tag.svelte';
	import Blog from './atoms/blog.svelte';
	import { fly } from 'svelte/transition';
    import { quintInOut } from 'svelte/easing';

	let animate = false;

	function actionWhenInViewport(e) {
		const observer = new IntersectionObserver((entries) => {
			if (entries[0].isIntersecting) {
				// element in viewport
				animate = true;
			} else {
				animate = false;
			}
		});

		observer.observe(e);
	}

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
	];
</script>

<div use:actionWhenInViewport class="sm:items-stretch p-16">
	{#if animate}
    <Tag text="Blogs" />
	<div transition:fly={{delay: 300, y:500, duration: 600, easing: quintInOut}} class="flex justify-center flex-wrap blogs-container" style="gap: 2rem;">
		{#each blogs as blog}
			<Blog title={blog.title} unixTime={blog.unixTimeInMS} href={blog.href} image={blog.image} />
		{/each}
	</div>
    {/if}
</div>

<style>
	.blogs-container {
		padding: 0 8rem;
	}
</style>
