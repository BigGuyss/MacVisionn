<script>
	import { onMount } from 'svelte';

	export let slides = [
		{
			id: 1,
			image: '/slider1.jpg',
			title: '3B Han Tasarımı',
			description: 'Terkedilmiş bir kasabadaki küçük bir hanı tasarladığım projem.',
			src: '3bmodelleme'
		},
		{
			id: 2,
			image: '/slider2.jpg',
			title: 'Qloque şıklığıyla zamanı yakala!',
			description: 'Zamanı verimli kullanan ve şıklığından ödün vermeyenlerin tercihi Qloque.',
			src: 'reklampazarlama'
		},
		{
			id: 3,
			image: '/slider3.jpg',
			title: 'VibesofChibi dünyasını keşfedin!',
			description:
				'Animasyonlarını gerçekleştirdiğim VibesofChibi’nin eğlenceli dünyasını keşfedin.',
			src: 'animasyon'
		}
	];

	onMount(() => {
		new Swiper('.anasayfa-slider', {
			slidesPerView: 1,
			spaceBetween: 30,
			mousewheel: true,
			loop: true,
			pagination: {
				el: '.swiper-pagination',
				clickable: true
			},
			navigation: {
				nextEl: '.swiper-button-next',
				prevEl: '.swiper-button-prev'
			}
		});
	});
</script>

<div
	class="my-8 mx-4 md:mx-auto swiper anasayfa-slider rounded-3xl border-b-16 border-gray bg-verydarkblue max-w-3xl text-center"
>
	<div class="swiper-wrapper">
		{#each slides as slide (slide.id)}
			<div class="swiper-slide relative">
				<a href="/{slide.src}">
					<img src={slide.image} alt="" class="opacity-40" />
					<div
						class=" py-1 md:absolute md:top-1/2 md:left-1/2 md:transform md:-translate-x-1/2 md:-translate-y-1/2"
					>
						<p
							class="font-bold text-lg md:text-3xl text-center md:text-center border-b-2 md:border-0 md:mb-4"
						>
							{slide.title}
						</p>
						<p class="py-2 md:p-0 font-bold text-sm md:text-lg">
							{slide.description}
						</p>
					</div>
				</a>
			</div>
		{/each}
	</div>
	<div class="swiper-button-next"></div>
	<div class="swiper-button-prev"></div>
	<div class="swiper-pagination hidden md:block"></div>
</div>

<style>
	div {
		--swiper-theme-color: #ffffff;
	}
</style>
