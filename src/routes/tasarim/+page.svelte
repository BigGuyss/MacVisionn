<script>
	import { onMount } from 'svelte';

	let slides = [
		{ src: '/tasarim/valor1.jpg' },
		{ src: '/tasarim/valor2.jpg' },
		{ src: '/tasarim/valor3.jpg' },
		{ src: '/tasarim/valor4.jpg' },
		{ src: '/tasarim/billboard1.jpg' },
		{ src: '/tasarim/billboard2.jpg' },
		{ src: '/tasarim/billboard3.jpg' },
		{ src: '/tasarim/billboard4.jpg' },
		{ src: '/tasarim/turkcell1.png' },
		{ src: '/tasarim/turkcell2.jpg' },
		{ src: '/tasarim/turkcell3.jpg' },
		{ src: '/tasarim/turkcell4.jpg' }
	];
	onMount(() => {
		let swiper = new Swiper('.mySwiper', {
			effect: 'coverflow',
			grabCursor: true,
			centeredSlides: true,
			slidesPerView: 'auto',
			coverflowEffect: {
				rotate: 50,
				stretch: 0,
				depth: 100,
				modifier: 1,
				slideShadows: true
			},
			navigation: {
				nextEl: '.swiper-button-next',
				prevEl: '.swiper-button-prev'
			},
			pagination: {
				el: '.swiper-pagination'
			}
		});
		swiper.on('slideChange', function () {
			let swiperEl = document.querySelector('.mySwiper');
			if (this.activeIndex >= 0 && this.activeIndex < 8) {
				swiperEl.style.backgroundColor = '#82223d';
			} else if (this.activeIndex >= 8) {
				swiperEl.style.backgroundColor = '#15274d';
			}
		});
		swiper.emit('slideChange');
	});
</script>

<div
	class="sticky md:fixed top-0 md:top-28 md:left-0 md:w-48 text-center md:rounded-r-3xl bg-verydarkblue z-40"
>
	<h2 class="p-1 md:p-2 font-bold md:text-xl">Tasarım</h2>
</div>

<div class="h-[calc(100vh-200px)] flex items-center bg-lightgray md:h-[calc(100vh-136px)]">
	<div class="swiper mySwiper">
		<div class="swiper-wrapper">
			{#each slides as slide}
				<div class="swiper-slide">
					<img class="md:h-[calc(100vh-136px)] mx-auto" src={slide.src} alt="" />
					<p class="absolute bottom-16 left-1/2 -translate-x-1/2 bg-black z-40">
						{slide.description ? slide.description : ''}
					</p>
				</div>
			{/each}
		</div>
		<div class="swiper-pagination"></div>
		<div class="swiper-button-next"></div>
		<div class="swiper-button-prev"></div>
	</div>
</div>

<style>
	div {
		--swiper-theme-color: #ffffff;
	}
</style>
