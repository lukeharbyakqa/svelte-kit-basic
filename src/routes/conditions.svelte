<script>
	let product = {
		name: 'T-Shirt',
		quantity: 0
	};

	function increment() {
		product.quantity += 1;
	}
</script>

<pre>CONDITIONS</pre>
{#if product.quantity >= 10}
	<div style="background-color: lightGreen; padding: 4px;">This product is in stock</div>
{:else if product.quantity == 0}
	<div style="background-color: pink; padding: 4px;">No more stock, boo!</div>
{:else}
	<div style="background-color: lemonChiffon; padding: 4px">Only a few left in stock</div>
{/if}
<p>Current: {product.name}. Quantity: {product.quantity}</p>
<button on:click={increment}>Increment</button>
