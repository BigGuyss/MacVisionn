<script>
	import '../app.css';
	import Navbar from '../components/Navbar.svelte';
	import { afterNavigate } from '$app/navigation';

	afterNavigate(() => {
		document.getElementById('main').scrollTo(0, 0);
	});
</script>

<head>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
	<link
		href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap"
		rel="stylesheet"
	/>
	<link
		href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600&display=swap"
		rel="stylesheet"
	/>
</head>

<header
	class="h-32 md:h-24 grid grid-cols-1 md:grid-cols-2 bg-verydarkblue text-white items-center text-center sticky top-0 z-50"
>
	<Navbar />
	<div class="bg-gray min-h-4 text-verydarkblue text-2xl font-bold md:col-span-2"></div>
</header>

<main
	id="main"
	class="h-[calc(100vh-168px)] md:h-[calc(100vh-136px)] snap-y snap-mandatory overflow-auto text-white"
>
	<slot />
</main>

<footer>
	<div
		class="flex items-center justify-center gap-4 w-full bg-verydarkblue sticky bottom-0 text-white p-2 z-50"
	>
		<a href="https://instagram.com/merttodemis" target="_blank"
			><img src="/iletisim/instagram.png" width="24px" alt="" /></a
		>
		<a href="https://youtube.com/@merttodemis" target="_blank"
			><img src="/iletisim/youtube.png" width="24px" alt="" /></a
		>
		<a href="https://linkedin.com/in/merttodemis" target="_blank"
			><img src="/iletisim/linkedin.png" width="24px" alt="" /></a
		>
		<a href="https://merttodemis.artstation.com" target="_blank"
			><img src="/iletisim/artstation.png" width="24px" alt="" /></a
		>
		<a href="https://behance.com/mertodemis" target="_blank"
			><img src="/iletisim/behance.png" width="24px" alt="" /></a
		>
	</div>
</footer>
