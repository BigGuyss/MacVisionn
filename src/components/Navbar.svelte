<script>
	import { onMount } from 'svelte';

	let links = [
		{ href: '/', text: 'Anasayfa' },
		{ href: '/hakkimda', text: 'Hakkımda' },
		{
			href: '',
			text: 'Çalışmalarım',
			dropdown: true,
			submenu: [
				{ href: '/3bmodelleme', text: '3B Modelleme' },
				{ href: '/reklampazarlama', text: 'Reklam/Pazarlama' },
				{ href: '/tasarim', text: 'Tasarım' },
				{ href: '/animasyon', text: 'Animasyon' }
			]
		},
		{ href: '/iletisim', text: 'İletişim' }
	];

	let dropdownIsOpen = false;

	function toggleDropdown() {
		dropdownIsOpen = !dropdownIsOpen;
	}

	function closeDropdown() {
		dropdownIsOpen = false;
	}

	onMount(() => {
		const handleClickOutside = () => {
			if (!event.target.closest('.group')) {
				closeDropdown();
			}
		};

		window.addEventListener('click', handleClickOutside);

		return () => {
			window.removeEventListener('click', handleClickOutside);
		};
	});
</script>

<h1 class="bannertext my-5 text-4xl font-bold col-span-1">MacVisionn</h1>

<nav class="flex md:gap-5 lg:gap-10 justify-evenly md:justify-center col-span-1">
	{#each links as { href, text, dropdown, submenu }}
		{#if dropdown}
			<div class="relative group">
				<button
					class="block rounded-md text-sm p-2 md:m-0 md:p-2 font-bold hover:bg-white hover:border-white hover:text-verydarkblue transition"
					on:click={() => toggleDropdown()}
				>
					{text}
					<div
						class="{dropdownIsOpen
							? 'block'
							: 'hidden'} absolute left-0 bg-white mt-2 rounded-md text-verydarkblue border border-gray"
					>
						{#each submenu as subitem}
							<a
								href={subitem.href}
								class="block px-4 py-2 hover:bg-verydarkblue hover:text-white rounded-xl"
								>{subitem.text}</a
							>
						{/each}
					</div>
				</button>
			</div>
		{:else}
			<a
				{href}
				class="block rounded-md text-sm p-2 md:m-0 md:p-2 font-bold hover:bg-white hover:border-white hover:text-verydarkblue transition"
			>
				{text}
			</a>
		{/if}
	{/each}
</nav>
