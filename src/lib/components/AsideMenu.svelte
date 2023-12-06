<script>
	import HomeIcon from '@icons/HomeIcon.svelte';
	import LibraryIcon from '@icons/LibraryIcon.svelte';
	import ListIcon from '@icons/ListIcon.svelte';
	import PlusIcon from '@icons/PlusIcon.svelte';
	import SearchIcon from '@icons/SearchIcon.svelte';
	import PillItem from '@components/PillItem.svelte';
	import PlaylistItem from '@components/PlaylistItem.svelte';
	import SideMenuItem from '@components/SideMenuItem.svelte';
	import playlists from '@fixtures/playlists.json';
</script>

<nav class="flex flex-col flex-1 gap-2 relative">
	<ul class="bg-zinc-900 rounded-lg p-2">
		<SideMenuItem><HomeIcon />Home</SideMenuItem>
		<SideMenuItem><SearchIcon />Search</SideMenuItem>
	</ul>

	<div class="flex flex-col flex-1 bg-zinc-900 rounded-lg gap-2 p-2 relative">
		<section class="flex flex-row justify-between p-2 items-center" aria-label="library-header">
			<a
				href="/#"
				class="flex flex-row gap-2 text-zinc-400 fill-zinc-400 hover:text-zinc-100 hover:fill-zinc-100 w-fit"
			>
				<LibraryIcon />
				<span>Your Library</span>
			</a>

			<a href="/#" class="p-2 fill-zinc-400 hover:fill-zinc-100 hover:bg-zinc-800 rounded-full">
				<PlusIcon />
			</a>
		</section>

		<section
			class="flex flex-row items-center flex-nowrap overflow-x-auto gap-2 p-2 text-sm shadow-inner"
			aria-label="filtering-header"
		>
			<PillItem title="Playlists" />
			<PillItem title="Artists" />
			<PillItem title="Albums" />
			<PillItem title="Podcasts" />
			<PillItem title="Local Files" />
			<PillItem title="Videos" />
		</section>

		<section
			class="flex flex-col flex-nowrap overflow-y-auto gap-2 p-2 relative h-96"
			aria-label="playlists"
		>
			<div class="flex flex-row justify-between items-center text-zinc-400 fill-zinc-400">
				<button class="rounded-full hover:bg-zinc-800 p-2"><SearchIcon /></button>
				<button class="flex flex-row items-center gap-2 hover:text-zinc-100 hover:fill-zinc-100">
					<span>Recently</span>
					<ListIcon />
				</button>
			</div>

			<ul class="flex flex-col">
				{#each playlists as playlist (playlist.name)}
					<PlaylistItem {playlist} />
				{/each}
			</ul>
		</section>
	</div>
</nav>
