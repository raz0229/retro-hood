<script>
	export let text = 'Tag Text';
</script>

<div class="tag m-32 flex" style="gap: 1rem;">
	<hr />
	<div class="text text-md">{text}</div>
</div>

<style>
	.tag .text {
		color: #6d6d6d;
		text-transform: uppercase;
	}

	hr {
		display: block;
		height: 3px;
        width: 55px;
		border: 0;
		border-top: 1px solid #6d6d6d;
		margin: 0.75rem 0;
		padding: 0;
	}
</style>
