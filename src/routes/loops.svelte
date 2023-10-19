<script>
	import GridTile from '$lib/GridTile.svelte';

	let products = [
		{
			name: 'T-Shirt',
			quantity: 0
		},
		{
			name: 'Mug',
			quantity: 30
		},
		{
			name: 'Sticker',
			quantity: 8
		},
		{
			name: 'Sweatshirt',
			quantity: 12
		}
	];

	function addProduct() {
		let cup = { name: 'cup', quantity: 4 };
		products = [cup, ...products];
	}
</script>

<pre>LOOPS</pre>
<GridTile />
<button on:click={addProduct}>Add product</button>
{#each products as product, i (product.name)}
	<div class="mb-10">
		<h3>{product.name}</h3>
		<input type="checkbox" name="" id="" />
		<div>{i}</div>
	</div>
{/each}

<style lang="scss">
	div {
		background-color: orange;

		h3 {
			color: #fff;
		}
	}
</style>
