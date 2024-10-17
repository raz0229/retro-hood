<script>

    export let item = {
        index : '01',
        title : 'Fabric Selection',
        details : 'Your dedicated representative will initially help you select the best fabric for your product.',
        color: 'black',
        detailGrey: false
    }

</script>

<div class="w-{item.width ?? '72'} mt-32 p-{item.padding ?? '0'} bg-[{item.backgroundColor ?? 'transaprent'}]">
    <h1 class="text-{item.indexColor ?? '[#6d6d6d]'} mt-4 mb-2 font-extralight text-2xl" style="line-height: 1.25rem;">
        {item.index}
    </h1>
    <h1 class="text-{item.titleColor ?? item.color} font-medium lg:text-3xl md:text-5xl text-3xl" style="line-height: 2.55rem;">
        {item.title}
    </h1>
    {#if item.detailGrey}
    <h1 class="text-[#6d6d6d] mt-12 font-light text-2xl" style="line-height: 1.25rem;">
        {item.details}
    </h1>
    {:else}
    <h1 class="text-{item.color} mt-12 font-light text-2xl" style="line-height: 1.25rem;">
        {item.details}
    </h1>
    {/if}
    
</div>