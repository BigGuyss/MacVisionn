<script>
	export let imgSrc;
	export let title;
	export let text;
	export let reverse = false;
	export let bordered = false;
</script>

<div
	class="max-w-7xl mx-auto flex flex-col {reverse
		? 'md:flex-row-reverse'
		: 'md:flex-row'} items-center"
>
	<div class="my-8 {reverse ? 'md:ml-12' : 'md:mr-12'}">
		<img
			src={imgSrc}
			class="mx-auto md:max-w-md lg:max-w-sm {bordered
				? 'border-verydarkblue rounded-full border-8'
				: 'border-none'}"
			alt=""
		/>
	</div>
	<div class="text-verydarkblue text-justify p-8 border-y-2 border-lightgray md:mx-auto">
		<h1 class="text-2xl mb-4">{title}</h1>
		<h2 class="text-lg">
			{text}
		</h2>
	</div>
</div>
