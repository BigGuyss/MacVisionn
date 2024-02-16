<script>
	import { onMount } from 'svelte';

	export let slides = [];
	export let title = '';
	export let description = '';
	let fullscreen = false;
	let id = Math.random().toString(36).substring(2); // Generate a unique ID for each component instance

	function toggleFullscreen() {
		fullscreen = !fullscreen;
	}

	onMount(() => {
		let swiper = new Swiper(`.calismalarim-slider-thumb-${id}`, {
			loop: true,
			spaceBetween: 10,
			slidesPerView: slides.length,
			freeMode: true,
			watchSlidesProgress: true
		});
		let swiper2 = new Swiper(`.calismalarim-slider-${id}`, {
			loop: true,
			spaceBetween: 10,
			navigation: {
				nextEl: '.swiper-button-next',
				prevEl: '.swiper-button-prev'
			},
			thumbs: {
				swiper: swiper
			}
		});
	});
</script>

<div
	class="flex flex-wrap lg:flex-nowrap items-center justify-evenly h-[calc(100vh-168px)] md:h-[calc(100vh-136px)]"
>
	<div class="pt-6 lg:p-0 {fullscreen ? 'w-full' : 'md:w-4/5 lg:w-2/5 w-5/6'}">
		<div class="swiper {`calismalarim-slider-${id}`} {fullscreen ? 'm-0' : 'm-4'}">
			<div class="swiper-wrapper">
				{#each slides as slide}
					<div
						class="swiper-slide"
						role="button"
						tabindex="0"
						on:click={() => {
							toggleFullscreen();
						}}
						on:keydown={(event) => {
							if (event.key === 'Enter') {
								toggleFullscreen();
							}
						}}
					>
						<img
							src={slide.image}
							class="rounded-xl border border-gray {fullscreen
								? 'w-screen lg:w-auto lg:h-[calc(100vh-136px)] mx-auto'
								: ''}"
							alt=""
						/>
					</div>
				{/each}
			</div>
			<div class="swiper-button-next"></div>
			<div class="swiper-button-prev"></div>
		</div>
		<div
			thumbsSlider=""
			class="swiper {`calismalarim-slider-thumb-${id}`} {fullscreen ? 'p-0' : 'px-4 pb-4'}"
		>
			<div class="swiper-wrapper">
				{#each slides as slide}
					<div class="swiper-slide {fullscreen ? 'hidden' : 'block'}">
						<img src={slide.image} class="rounded-3xl border border-gray" alt="" />
					</div>
				{/each}
			</div>
		</div>
	</div>
	<div class="max-w-sm md:max-w-md px-4 {fullscreen ? 'hidden' : 'block'}">
		<h2 class="text-xl text-center font-bold mb-4 pb-4 md:text-2xl border-b-2 border-b-gray">
			{title}
		</h2>
		<p class="pb-20 md:p-0 text-justify md:text-lg">
			{description}
		</p>
	</div>
</div>
