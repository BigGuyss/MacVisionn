<script>
	import SliderWithThumbs from '../../components/SliderWithThumbs.svelte';
	import Qloque from '../../components/Qloque.svelte';
</script>

<body class="text-verydarkblue">
	<div
		class="sticky md:fixed top-0 md:top-28 md:left-0 md:w-48 text-center md:rounded-r-3xl bg-verydarkblue text-white z-40"
	>
		<h2 class="p-1 md:p-2 font-bold md:text-xl">3B Modelleme</h2>
	</div>

	<div class="snap-start">
		<Qloque />
	</div>
	<div class="snap-start bg-lightgray">
		<SliderWithThumbs
			title="3B Han Tasarımı"
			description="Arkadaşlarımla geliştirdiğimiz oyunun bir kasabasını oluşturmak için başladığım projede olayların gerçekleşeceği ilk mekan olarak bu hanı tasarladım. Tasarımı blender programıyla gerçekleştirdim."
			slides={[
				{ image: '/3bmodelleme/han/SS_hantasarımı1.png' },
				{ image: '/3bmodelleme/han/SS_hantasarımı2.png' },
				{ image: '/3bmodelleme/han/SS_hantasarımı3.png' }
			]}
		/>
	</div>
	<div class="snap-start">
		<SliderWithThumbs
			title="3B Low Poly Şehir Tasarımı"
			description="Üniversitede aldığım modelleme dersinin ödevi amacıyla gerçekleştirdiğim Low Poly Şehir tasarımı."
			slides={[
				{ image: '/3bmodelleme/sehir/1.png' },
				{ image: '/3bmodelleme/sehir/2.png' },
				{ image: '/3bmodelleme/sehir/3.png' },
				{ image: '/3bmodelleme/sehir/4.png' },
				{ image: '/3bmodelleme/sehir/5.png' },
				{ image: '/3bmodelleme/sehir/6.png' }
			]}
		/>
	</div>
</body>

<style>
	body {
		--swiper-theme-color: #0a1128;
	}
</style>
