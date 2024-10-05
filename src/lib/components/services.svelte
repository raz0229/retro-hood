<script>
    import Tag from "./atoms/tag.svelte";
    import Service from "./atoms/service.svelte";

    const services = [
        {
            name: 'Manufacturing'
        },
        {
            name: 'Procurement'
        },
        {
            name: 'Printing'
        },
        {
            name: 'Treatment'
        },
        {
            name: 'Sewing'
        },
        {
            name: 'Warehousing'
        },
        {
            name: 'Quality Control'
        }
    ]
</script>

<div class="sm:items-stretch p-16">
    <Tag text="Services"/>

    {#each services as service}
        <Service serviceName="{service.name}"/>
    {/each}
</div>

