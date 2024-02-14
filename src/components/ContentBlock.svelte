<script>
	export let imgSrc;
	export let title;
	export let text;
	export let reverse = false;
	export let bordered = false;
</script>

<div
	class="max-w-7xl mx-auto flex flex-col {reverse
		? 'lg:flex-row-reverse'
		: 'lg:flex-row'} items-center"
>
	<div class="my-8 {reverse ? 'lg:ml-12' : 'lg:mr-12'}">
		<img
			src={imgSrc}
			class="mx-auto lg:max-w-sm {bordered
				? 'border-verydarkblue rounded-full border-8'
				: 'border-none'}"
			alt=""
		/>
	</div>
	<div class="text-verydarkblue text-justify p-8 border-y-2 border-lightgray lg:mx-auto">
		<h1 class="text-2xl mb-4">{title}</h1>
		<h2 class="text-md">
			{text}
		</h2>
	</div>
</div>
