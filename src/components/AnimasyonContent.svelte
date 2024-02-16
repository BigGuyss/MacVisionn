<script>
	export let src = '';
	export let title = '';
	export let description = '';
	export let description2 = '';
	export let width = '';
	export let height = '';
	export let href = '';
	export let img_src = '';
</script>

<div
	class="flex flex-wrap lg:flex-nowrap justify-center items-center lg:items-end h-[calc(100vh-168px)] md:h-[calc(100vh-136px)]"
>
	<div class="mt-2 lg:m-0 w-full h-2/5 lg:h-full lg:w-full">
		<iframe
			class="w-full h-full p-8 lg:p-16"
			{width}
			{height}
			src={`https://www.youtube.com/embed/${src}`}
			title=""
			frameborder="0"
			allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
			allowfullscreen
		>
		</iframe>
	</div>
	<div class=" px-4 lg:p-16 lg:max-w-lg">
		<h2 class="text-center font-bold pb-4 lg:text-2xl border-b-2 border-b-gray">
			{title}
		</h2>
		<p class="text-justify my-4">
			{description}
		</p>
		<a class="flex justify-center gap-2 mb-2 items-center" {href} target="_blank">
			<img src={img_src} width="32px" alt="" />
			<h2>{description2}</h2></a
		>
	</div>
</div>
