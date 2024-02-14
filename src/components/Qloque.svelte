<script>
	import { onMount } from 'svelte';
	import Toggle from 'svelte-switcher/Toggle.svelte';

	let genderswitch = false;
	let slides = [
		[
			{ image: '/3bmodelleme/qloque/erkek1.jpg' },
			{ image: '/3bmodelleme/qloque/erkek2.jpg' },
			{ image: '/3bmodelleme/qloque/erkek3.jpg' }
		],
		[
			{ image: '/3bmodelleme/qloque/kadin1.jpg' },
			{ image: '/3bmodelleme/qloque/kadin2.jpg' },
			{ image: '/3bmodelleme/qloque/kadin3.jpg' }
		]
	];
	let title = 'Qloque Saat Tasarımı';
	let description = `Qloque, klasik saat görünümünü seven ancak aynı zamanda modern bir saat arayışında olanlar için özel olarak tasarlanmış bir saat markasıdır. Bu yeni konsept saatlerde dakika ve saniye ibresi yerine dakika ve saniyeyi sayısal olarak gösteren sayaçlar bulunmaktadır.`;
	let fullscreen = false;
	let id = Math.random().toString(36).substring(2); // Generate a unique ID for each component instance

	function toggleFullscreen() {
		fullscreen = !fullscreen;
	}

	onMount(() => {
		let swiper = new Swiper(`.calismalarim-slider-thumb-${id}`, {
			loop: true,
			spaceBetween: 10,
			slidesPerView: 3,
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
	<div class="pt-6 md:p-0 {fullscreen ? 'w-full' : 'md:w-4/5 lg:w-2/5 min-w-96'}">
		<div class="swiper {`calismalarim-slider-${id}`} {fullscreen ? 'm-0' : 'm-4'}">
			<div class="swiper-wrapper">
				{#each slides[genderswitch ? 1 : 0] as slide}
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
				{#each slides[genderswitch ? 1 : 0] as slide}
					<div class="swiper-slide {fullscreen ? 'hidden' : 'block'}">
						<img src={slide.image} class="rounded-3xl border border-gray" alt="" />
					</div>
				{/each}
			</div>
			<div
				id="custom-styling"
				class="flex md:hidden justify-center items-center pt-2 gap-2 font-bold"
			>
				<span>Erkek</span>
				<Toggle id="svelte-toggle" name="svelte-toggle" bind:checked={genderswitch} />
				<span>Kadın</span>
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
		<div
			id="custom-styling"
			class="hidden md:flex justify-center items-center gap-2 md:pt-8 lg:pt-16 font-bold"
		>
			<span>Erkek</span>
			<Toggle id="svelte-toggle" name="svelte-toggle" bind:checked={genderswitch} />
			<span>Kadın</span>
		</div>
	</div>
</div>

<style>
	#custom-styling > :global(.svelte-toggle .svelte-toggle--track) {
		width: 60px;
		height: 30px;
		border-radius: 4px;
		background-color: #001f54;
	}

	#custom-styling > :global(.svelte-toggle .svelte-toggle--thumb) {
		height: 29px;
		width: 28px;
		border-radius: 4px;
	}
	#custom-styling > :global(.svelte-toggle.svelte-toggle--checked .svelte-toggle--thumb) {
		left: 32px;
	}
	#custom-styling > :global(.svelte-toggle.svelte-toggle--checked .svelte-toggle--track) {
		background-color: #e4d7cf;
	}
</style>
