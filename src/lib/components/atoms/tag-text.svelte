<script>
    export let lines = [
        'We go beyond manufacturing',
        'best quality. Sounds too',
        'good to be true?'
    ]
</script>

<h4 class="lineup-text text-bold text-3xl text-black">
    {#each lines as line}
    {line} <br>
    {/each}
</h4>

<style>
    .lineup-text {
        margin: 0rem 12rem;
    }

    @media only screen and (max-width: 950px) {
		.lineup-text {
        margin: 0rem 6rem;
    }
	}

	@media only screen and (max-width: 600px) {
		.lineup-text {
        margin: 0rem 2rem;
    }
	}
</style>