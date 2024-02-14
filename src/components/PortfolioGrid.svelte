<script>
	import PortfolioItem from './PortfolioItem.svelte';
	export let items = [
		{
			href: '/3bmodelleme',
			src: '/3BModelleme.jpg',
			alt: '',
			title: '3B Modelleme'
		},
		{
			href: '/reklampazarlama',
			src: '/ReklamPazarlama.jpg',
			alt: '',
			title: 'Reklam/Pazarlama'
		},
		{
			href: '/tasarim',
			src: '/Tasarım.jpg',
			alt: '',
			title: 'Tasarım'
		},
		{
			href: '/animasyon',
			src: '/Animasyon.jpg',
			alt: '',
			title: 'Animasyon/Video'
		}
	];
</script>

<div
	class="p-4 grid grid-cols-2 gap-4 items-center justify-items-center md:flex md:justify-center text-darkblue font-bold w-full bg-lightgray"
>
	{#each items as item (item.href)}
		<PortfolioItem href={item.href} src={item.src} alt={item.alt} />
	{/each}
</div>
