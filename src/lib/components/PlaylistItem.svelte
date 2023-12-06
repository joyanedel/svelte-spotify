<script lang="ts">
	export let playlist: {
		name: string;
		description: string;
		src: string;
		tracks: {
			title: string;
			artist: string;
			album: string;
		}[];
	};
</script>

<a class="rounded-lg hover:bg-zinc-800 w-full h-20 align-middle" href="/#">
	<div class="flex flex-row items-center gap-2 p-2 h-full">
		<img
			class="rounded-md object-cover aspect-square"
			src={playlist.src}
			alt={playlist.name}
			height="56"
			width="56"
		/>
		<div class="flex flex-col flex-nowrap">
			<span class="text-zinc-400 fill-zinc-400 font-bold overflow-y-hidden">{playlist.name}</span>
			<span class="text-zinc-400 fill-zinc-400 text-sm overflow-y-hidden text-clip"
				>{playlist.description}</span
			>
		</div>
	</div>
</a>
