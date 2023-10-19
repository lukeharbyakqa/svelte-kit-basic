<script>
	let quanitiy = 0;

	function addToCart() {
		inventory = [...inventory, quanitiy];
		quanitiy = ++quanitiy;
		inventory = inventory;
		user.name = 'Luke';
	}

	function IncreasePrice() {
		price = price + 2;
	}

	function handleClick(string) {
		console.log(string);
	}

	$: remaining = 10 - quanitiy;
	let price = 5;
	$: totalCost = quanitiy * price;
	let inventory = [1, 2, 3];
	let user = { name: 'Stephen' };
	$: if (quanitiy >= 10) {
		console.log(`the quantity is ${quanitiy}`);
	}
</script>

<pre>INDEX</pre>
<p>Your shopping cart has {quanitiy} items</p>
<button on:click={addToCart}>Add to Cart</button>
<h2>{inventory}</h2>
{user.name}
<p>Remaining: {remaining}</p>
<p>Item price: ${price}</p>
<button on:click={IncreasePrice}>Increase price</button>
<p>Total cost: ${totalCost.toFixed(2)}</p>

<button on:click={() => handleClick('Twats')}>Click me!</button>
<div
	role="presentation"
	style="background-color: lawngreen; padding: 20px;"
	on:mousemove|self|once={(event) => handleClick(event)}
	on:keydown
>
	<div style="background-color: orange; padding: 10px;" />
</div>
