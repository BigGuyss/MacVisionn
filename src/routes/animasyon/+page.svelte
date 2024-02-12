<script>
	import AnimasyonContent from '../../components/AnimasyonContent.svelte';
</script>

<div class="bg-purple">
	<div
		class="sticky md:fixed top-0 md:top-28 md:left-0 md:w-48 text-center md:rounded-r-3xl bg-verydarkblue z-40"
	>
		<h2 class="p-1 md:p-2 font-bold md:text-xl">Animasyon</h2>
	</div>

	<div class="snap-start bg-[url('/animasyon/chibibackground.jpg')] bg-cover">
		<AnimasyonContent
			src="x4bt06KywcY"
			title="Vibes of Chibi"
			description="Chibi üniversite arkadaşlarımla hayata geçirdiğim bir animasyon karakteridir.  İnsanların ortak hislerini anlatan kimi zaman gündemle ilgili kimi zaman da popüler akımları takip ederek oluşturduğumuz içerikleri takipçilerimizin beğenisine sunduk. Bu projedeki rolüm yazılan içeriklerin kurgularının yapılarak animasyonunu gerçekleştirmekti."
			href="https://instagram.com/vibesofchibi"
			;
			img_src="/iletisim/instagram.png"
			description2="@vibesofchibi"
		/>
	</div>
	<div class="snap-start bg-[url('/animasyon/qloquebackground.jpg')] bg-cover text-verydarkblue">
		<AnimasyonContent
			src="4kMAN15K0Rw"
			title="Qloque Saat Animasyonu"
			description="Blender uygulaması ile oluşturduğum Qloque saatlerinin reklam animasyonu."
			href="https://youtube.com/@merttodemis"
			;
			img_src="/iletisim/youtube.png"
			description2="@merttodemis"
		/>
	</div>
</div>
