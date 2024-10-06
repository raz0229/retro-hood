<script>
	export let title = 'Lorem Ipsum Blog Title';
	export let unixTime = 1728187652781;
	export let href = '#';
	export let image = 'blogs/cover.jpg';

	const months = [
		'Jan',
		'Feb',
		'Mar',
		'Apr',
		'May',
		'Jun',
		'Jul',
		'Aug',
		'Sep',
		'Oct',
		'Nov',
		'Dec'
	];
</script>

<div style="max-width: 350px;" class="block rounded-lg bg-white shadow-2xl">
	<a class="text-center" href="#!">
		<img style="border-radius: 1rem;" class="p-2" src={image} alt="" />
	</a>
	<div class="p-6 text-black">
		<div class="flex" style="gap: 1rem;">
            <div
			class="date"
			style="min-width: 3rem;
                    text-align: center;
                    line-height: 0.75rem;"
		>
			<div
				class="pre pt-2 bg-[#e5e3e3]"
				style="border-top-right-radius: 0.69rem; border-top-left-radius: 0.69rem;"
			>
				<div class="date text-red-600" style="font-weight: 600; font-size: large;">
					{new Date(unixTime).getDate()}
				</div>
				<div class="month p-1" style="font-weight: 400; font-size: smaller">
					{months[new Date(unixTime).getMonth()]}
				</div>
			</div>
			<div
				style="border-bottom-right-radius: 0.69rem; border-bottom-left-radius: 0.69rem;"
				class="year bg-black text-white text-[0.75rem] p-1"
			>
				{new Date(unixTime).getFullYear()}
			</div>
		</div>
        <h5 class="mb-2 text-xl card-title font-medium leading-tight">{title}</h5>
		
        </div>
		<a class="flex justify-end text-lg font-light underline underline-offset-2 text-black hover:text-red-600"
            style="cursor: pointer;"
        {href}>Read more</a>
	</div>
</div>

<style>
	.card-title {
		text-transform: uppercase;
	}
</style>
