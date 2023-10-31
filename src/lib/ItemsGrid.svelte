<script>
	import { getContext } from 'svelte';
	export let items = getContext('newItemsContext');
</script>

<div class="flex items-center">
	{#each items as item}
		<div
			class="relative m-2 flex h-40 w-1/2 items-center justify-center overflow-hidden bg-white/20"
		>
			<img src={item.src} class="h-full" alt="" />
			<div class="absolute bottom-0 right-0 bg-black p-2 text-white">{item.name}</div>
		</div>
	{/each}
</div>
