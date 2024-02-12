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
		new Swiper(`.calismalarim-slider-${id}`, {
			loop: true,
			spaceBetween: 10,
			navigation: {
				nextEl: '.swiper-button-next',
				prevEl: '.swiper-button-prev'
			}
		});
	});
</script>

<div
	class="flex flex-wrap lg:flex-nowrap lg:items-center justify-evenly h-[calc(100vh-168px)] md:h-[calc(100vh-136px)]"
>
	<div class="pt-6 md:p-0 {fullscreen ? 'w-full' : 'w-1/2 min-w-96'}">
		<div class="swiper {`calismalarim-slider-${id}`} {fullscreen ? 'm-0' : 'm-4'}">
			<div class="swiper-wrapper">
				{#each slides as slide}
					<div
						class="swiper-slide"
						role="button"
						tabindex="0"
						on:click={() => {
							if (window.innerWidth > 768) {
								toggleFullscreen();
							}
						}}
						on:keydown={(event) => {
							if (event.key === 'Enter' && window.innerWidth > 768) {
								toggleFullscreen();
							}
						}}
					>
						<img
							src={slide.image}
							class="rounded-xl border border-gray {fullscreen
								? 'h-[calc(100vh-136px)] mx-auto'
								: ''}"
							alt=""
						/>
					</div>
				{/each}
			</div>
			<div class="swiper-button-next"></div>
			<div class="swiper-button-prev"></div>
		</div>
	</div>
	<div class="max-w-sm md:max-w-lg px-4 {fullscreen ? 'hidden' : 'block'}">
		<h2 class="text-lg text-center font-bold mb-4 pb-4 md:text-2xl border-b-2 border-b-gray">
			{title}
		</h2>
		<p class="pb-20 lg:p-0 text-justify md:text-xl">
			{description}
		</p>
	</div>
</div>
