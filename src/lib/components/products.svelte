<script>
	import Tag from './atoms/tag.svelte';
	import TagText from './atoms/tag-text.svelte';
	import Grid from './grid.svelte';
</script>

<div class="sm:items-stretch p-16">
	<Tag text="Products" />
	<TagText lines={['Explore our collection', 'and experience the art of style']} />
    <Grid />

</div>
