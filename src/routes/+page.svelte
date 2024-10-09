<script>
    import Hero from "$lib/components/hero.svelte";
    import Services from "$lib/components/services.svelte";
    import Blogs from "$lib/components/blogs.svelte";
    import Slider from "$lib/components/slider.svelte";
    import Products from "$lib/components/products.svelte";
    import WhyUs from "$lib/components/why-us.svelte";

    const services = [
		{
			name: 'Manufacturing',
			image: 'services/manufacturing.jpg',
			details:
				"From the start of your project, you'll have a dedicated Client Account Manager ensuring a smooth transition through every stage—initial concept, sampling, development, and ultimately production. Our expert teams - client managers, developers, and merchandising specialists - respond swiftly to your needs. We deliver innovative solutions through continuous research and testing, prioritizing sustainability."
		},
		{
			name: 'Procurement',
			image: 'services/procurement.jpg',
			details:
				'Our extensive procurement division sources diverse fabrics globally, offering everything from basic single jersey to high-quality 500 gsm loopback cotton and terry fleece. We partner with suppliers across Pakistan to guarantee quality and environmental commitment, offering organic cotton, viscose, poly, and various blends.'
		},
		{
			name: 'Printing',
			image: 'services/printing.jpg',
			details:
				'Our state-of-the-art printing factory employs various techniques, including heat-sensitive printing, heat transfer, and digital printing on advanced TAS machines. With cutting-edge equipment, we ensure a high-quality product with a monthly output of 10,000 – 13,000 panels.'
		},
		{
			name: 'Treatment',
			image: 'services/treatment.jpg',
			details:
				'Our in-house Tajima embroidery machines, stone application, heat transfers, and other specialist equipment ensure premium quality.We also collaborate with trusted vendors for unique finishes like tie-dyeing and marble washing, using eco-friendly, water-based inks.'
		},
		{
			name: 'Sewing',
			image: 'services/sewing.jpg',
			details:
				'With 10 dedicated full-time operators across seven lines, our daily output can reach 100 units. Our team, skilled in using 3-5 different machine types, ensures diverse, high-quality products with minimal downtime.',
            subdetails: [
                {
                    name: 'Fabric Warehouse',
                    details: 'Maximize your fabric\'s potential with our 390 square per meter warehouse, storing up to 7,000 fabrics with precision and care.'
                },
                {
                    name: 'Trims Warehouse',
                    details: 'Streamline your trim storage with our 50 square per meter warehouse, expertly organizing and safeguarding your valuable trim collections.'
                },
                {
                    name: 'Finished Goods Warehouse',
                    details: 'Secure and efficient storage for your finished goods in our 100 square per meter warehouse, equivalent to 2 x 40 ft containers.'
                },
                {
                    name: 'Overstock and assets warehouse',
                    details: 'Optimize your storage needs with our 20 square per meter overstock and asset warehouse, expertly handling excess inventory and valuable assets.'
                },
            ]
		},
		{
			name: 'Warehousing',
			image: 'services/warehousing.jpg',
			details:
				'We provide comprehensive storage and warehouse solutions, managing individual store packing, direct dispatch, and specialized processing for department stores. Our ERP system ensures transparency and efficiency in managing goods movement and storage.'
		},
		{
			name: 'Quality Control',
			image: 'services/quality-control.jpg',
			details:
				'Adhering to international AQL 2.5 standards, we conduct AQL 1.5 final inspections and additional internal QC checkpoints at each production stage. Our testing facility ensures every garment meets durability, colorfastness, tear strength, weight, fabric twist, and shrinkage standards'
		}
	];
</script>

<div class="container">
    <Hero />
    <WhyUs />
    <Services services="{services}" />
</div>

<div class="container-white">
    <Products />
    <Slider />
    <Blogs />
</div>



<style>
    .container, .container-white {
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