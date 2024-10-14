<script>
    export let text = 'Get a quote'

	let sourceImage = 'arrow-slanted.png'


	const hoverHandler = () => {
		console.log('Hovered ', text)
		sourceImage = 'arrow-slanted-white.png'
	}

	const hoverLeave = () => {
		sourceImage = 'arrow-slanted.png';
	}

</script>
<div 
	on:mouseenter={hoverHandler}
	on:mouseleave={hoverLeave}
	on:click={()=>location.href = '/contact-us'}
	class="quote relative mt-12 ml-16">
    <div class="circle-arrow absolute">
        <div class="svg">
            <img src="{sourceImage}" alt="" />
        </div>
    </div>
    <button>&nbsp;{text}&nbsp;</button>
</div>

<style>

	.quote {
		transition: all 0.3s ease;
		cursor: pointer;
	}

    	.quote button {
		border-radius: 20px;
		background-color: #cb0f0f;
		padding: 0.2rem 1rem;
		color: #e2e2e2;
		z-index: 9;
		position: inherit;
		transition: background-color 0.3s ease;
	}

	.quote:hover {
		transform: scale(1.15);
	}

	.quote:hover button {
		color: #cb0f0f;
		background-color: #fff;
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
		transition: all 0.3s ease;
	}

	.quote:hover .circle-arrow {
		border: solid 1px #ffffff;
		background-color: #cb0f0f;
	}

	.circle-arrow > .svg img {
		width: 1.6rem;
		transition: transform 0.4s ease;
	}

	.quote:hover .circle-arrow > .svg img {
		transform: translate(90%, -90%);
	}
</style>