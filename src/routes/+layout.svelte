<script>
	import CartItemsStore from '../Store.js';
	import ShoppingCart from '$lib/ShoppingCart.svelte';
	import Modal from '$lib/Modal.svelte';
	import '../app.css';

	let showCart = false;
	let cartCount = 0;

	$: cartItems = $CartItemsStore;
	$: {
		cartCount = 0;
		cartItems.forEach((item) => {
			cartCount += item.quantity;
		});
	}
	function addItemToCart(event) {
		cartItems = [...cartItems, event.detail.item];
	}

	let showModal = true;
</script>

<div>
	{#if showModal}
		<Modal on:click={() => (showModal = false)}>
			<div slot="title">Modal title</div>
			<div slot="content">20% off in December, hurry</div>
			<div slot="cta">
				<button on:click={() => (showModal = false)}>OK</button>
			</div>
		</Modal>

		<Modal on:click={() => (showModal = false)}>
			<div slot="content">20% off in December, hurry</div>
			<div slot="cta" let:hover={hovering}>
				<button on:click={() => (showModal = false)}
					>{#if hovering}Are you sure you want to close? {:else} OK{/if}</button
				>
			</div>
		</Modal>
	{/if}
	<div>
		<nav class="flex items-center border-b border-zinc-700 p-4 lg:px-6 bg-black">
			<div class="flex w-full items-center justify-between">
				<div class="mr-4">
					<a href="/" class="">
						<picture>
							<source srcset="/svelte_logo.png" type="image/png" />
							<img src="/svelte_logo.png" alt="Svelte Logo" class="h-8" />
						</picture>
					</a>
				</div>
				<button
					on:click={() => {
						showCart = true;
					}}
					class="uppercase text-white flex items-center"
				>
					<div>Cart</div>
					<div
						class="w-5 h-5 ml-2 text-black bg-white rounded-full flex items-center justify-center text-xs font-bold"
					>
						{cartCount}
					</div>
				</button>
			</div>
		</nav>
	</div>
	<div class="relative">
		{#if showCart}
			<ShoppingCart
				on:click={() => {
					showCart = false;
				}}
				on:addItemToCart={addItemToCart}
			/>
		{/if}
		<slot />
	</div>
</div>
