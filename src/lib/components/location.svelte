<script>
    import Tag from "./atoms/tag.svelte";
    import ActionButton from "./atoms/action-button.svelte";
</script>

<div class="container sm:items-stretch lg:p-16 md:p-8 p-4">
    <Tag text="Location" />
    <h1 class="lg:pl-48 md:pl-20 pl-2 text-white font-semibold text-5xl text-white">
        See us <br> in Pakistan
    </h1>
    <h1 class="lg:pl-48 mt-8 md:pl-20 pl-2 text-[#6d6d6d] font-light text-2xl text-white">
        Let's meet up face to face sometimes
    </h1>

    <div class="maps mt-8 flex justify-center">
        <div style="max-width:100%;overflow:hidden;color:red;"><div id="embedded-map-display" style="height:100%; width:100%;max-width:100%;"><iframe style="height:100%;width:100%;border:0;" frameborder="0" src="https://www.google.com/maps/embed/v1/search?q=paragon+city+dha+phase+1&key=AIzaSyBFw0Qbyq9zTFTd-tUY6dZWTgaQzuU17R8"></iframe></div><a class="googl-ehtml" href="https://www.bootstrapskins.com/themes" id="grab-map-data">premium bootstrap themes</a><style>#embedded-map-display img.text-marker{background:none!important;}</style></div>
    </div>

    <div class="lg:flex md:block sm:block justify-around">
        <div>
            <h1 class="lg:pl-48 mt-8 md:pl-20 pl-2 text-[#6d6d6d] font-light text-2xl text-white">
                Paragon city near DHA PHASE 1
            </h1>
            <h1 class="lg:pl-48 md:pl-20 pl-2 text-white font-semibold text-3xl text-white">
                Lahore Pakistan
            </h1>
        </div>
        <ActionButton text="Find us on maps" />
    </div>
    

</div>


<style>
    iframe {
        filter: invert(90%) brightness(70%);
        transition: all 0.3s ease;
    }

    iframe:hover {
        filter: invert(10%);
    }

    .maps div {
        margin-top: 2rem;
        width:500px;
        height:350px
    }

    @media only screen and (max-width: 850px) {
		.maps div {
            width:400px;
            height:290px
        }
	}

	@media only screen and (max-width: 600px) {
		.maps div {
            width:300px;
            height:190px
        }
	}
	
</style>