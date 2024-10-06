<script>
    import Tag from "./atoms/tag.svelte";
    import Carousel from "./atoms/carousel.svelte";
    import TagText from "./atoms/tag-text.svelte";

    let images = [
      'lineup/product.jpg',
      'lineup/product.jpg',
      'lineup/product.jpg',
      'lineup/product.jpg'
    ];

    let lines = [
        'We go beyond manufacturing',
        'best quality. Sounds too',
        'good to be true?'
    ]

</script>

<div class="sm:items-stretch p-16">
    <Tag text="Lineup" />
    <TagText lines={lines} />
    <Carousel
        bind:images
    />
</div>