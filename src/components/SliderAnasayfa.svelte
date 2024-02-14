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
	class="my-8 mx-auto swiper anasayfa-slider rounded-3xl border-b-16 border-gray bg-verydarkblue w-5/6 lg:max-w-3xl text-center"
>
	<div class="swiper-wrapper">
		{#each slides as slide (slide.id)}
			<div class="swiper-slide relative">
				<a href="/{slide.src}">
					<img src={slide.image} alt="" class="opacity-40" />
					<div
						class=" py-1 lg:absolute lg:top-1/2 lg:left-1/2 lg:transform lg:-translate-x-1/2 lg:-translate-y-1/2"
					>
						<p
							class="font-bold text-lg lg:text-3xl text-center lg:text-center border-b-2 lg:border-0 lg:mb-4"
						>
							{slide.title}
						</p>
						<p class="py-2 lg:p-0 font-bold text-sm lg:text-lg">
							{slide.description}
						</p>
					</div>
				</a>
			</div>
		{/each}
	</div>
	<div class="swiper-button-next"></div>
	<div class="swiper-button-prev"></div>
	<div class="swiper-pagination hidden lg:block"></div>
</div>

<style>
	div {
		--swiper-theme-color: #ffffff;
	}
</style>
