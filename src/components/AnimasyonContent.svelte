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
	class="flex flex-wrap lg:flex-nowrap justify-center items-center md:items-end h-[calc(100vh-168px)] md:h-[calc(100vh-136px)]"
>
	<div class="mt-2 md:m-0 w-full">
		<iframe
			class="w-full h-64 md:h-[calc(100vh-136px)] p-8 md:p-16"
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
	<div class="px-16 md:p-16 md:max-w-lg">
		<h2 class="text-center font-bold pb-4 md:text-2xl border-b-2 border-b-gray">
			{title}
		</h2>
		<p class="text-justify md:text-xl my-4">
			{description}
		</p>
		<a class="flex justify-center gap-2 mb-2 items-center" {href} target="_blank">
			<img src={img_src} width="32px" alt="" />
			<h2>{description2}</h2></a
		>
	</div>
</div>
