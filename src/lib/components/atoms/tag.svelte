<script>
	export let text = 'Tag Text';
	export let color = '#6d6d6d';
</script>

<div class="tag flex" style="gap: 1rem;">
	<hr style="border-top: 1px solid {color};" />
	<div class="text text-md text-[{color}]">{text}</div>
</div>

<style>

	.tag {
		margin: 8rem;
	}

	.tag .text {
		/* color: #6d6d6d; */
		text-transform: uppercase;
	}

	hr {
		display: block;
		height: 3px;
        min-width: 55px;
		border: 0;
		margin: 0.75rem 0;
		padding: 0;
	}

	@media only screen and (max-width: 950px) {
		.tag {
			margin: 5rem;
		}
	}

	@media only screen and (max-width: 600px) {
		.tag {
			margin: 2rem;
		}
	}
</style>
