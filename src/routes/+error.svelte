<div class="container-white sm:items-stretch p-16">
    <div class="flex justify-center">
        <div class="image">
            <img style="width: 30rem;" src="404.png" alt="404">
        </div>
    </div>
    <div class="flex justify-center">
        <button on:click={()=>location.href = '/'}>
            Go Back
        </button>
    </div>
</div>

<style>

    button {
        text-align: center;
        font-weight: 400;
        font-size: 1.5rem;
        border-radius: 8px;
        padding: 0.3rem 1rem;
        background-color: #cb0f0f;
        color: #f8f8f8;
        cursor: pointer;
        transition: background-color 0.3s ease;
        box-shadow: 3cap;
    }

    button:hover {
        background-color: #b00b0b;
    }

	.container,
	.container-white {
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