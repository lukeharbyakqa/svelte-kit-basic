<!-- <script>
	import GridTile from '$lib/GridTile.svelte';
	import ShoppingCart from '$lib/ShoppingCart.svelte';

	let products = [
		{
			title: 'Mug',
			cost: '$10',
			src: '/path.png'
		},
		{
			title: 'Shirt',
			cost: '$10',
			src: '/path.png'
		}
	];

	let showCart = true;
</script>

<pre>INDEX</pre>
{#each products as product (product.title)}
	<GridTile products />
{/each}
<div class="relative">
	relative
	{#if showCart}
		<ShoppingCart />
	{/if}
</div> -->
