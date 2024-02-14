<script>
	import AnimasyonContent from '../../components/AnimasyonContent.svelte';
</script>

<div class="bg-purple">
	<div
		class="sticky lg:fixed top-0 lg:top-28 lg:left-0 lg:w-48 text-center lg:rounded-r-3xl bg-verydarkblue z-40"
	>
		<h2 class="p-1 lg:p-2 font-bold lg:text-xl">Animasyon</h2>
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
