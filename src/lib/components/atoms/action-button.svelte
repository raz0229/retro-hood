<script>
    export let text = 'Get a quote'
</script>
<div class="quote relative mt-12 ml-16">
    <div class="circle-arrow absolute">
        <div class="svg">
            <img src="arrow-slanted.png" alt="" />
        </div>
    </div>
    <button>&nbsp;{text}&nbsp;</button>
</div>

<style>
    	.quote button {
		border-radius: 20px;
		background-color: #cb0f0f;
		padding: 0.2rem 1rem;
		color: #e2e2e2;
		z-index: 9;
		position: inherit;
		transition: background-color 0.3s ease;
	}

	.quote button:hover {
		background-color: #b51111;
	}

	.circle-arrow {
		border-radius: 50%;
		border: solid 1px #6d6d6d;
		height: 5rem;
		width: 5rem;
		top: -1.6rem;
		left: -4rem;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.circle-arrow > .svg img {
		width: 1.3rem;
	}
</style>