<script>
	let hover = false;
</script>

<div class="modal p-4 rounded-md" on:click|self on:keydown role="presentation">
	{#if $$slots.title}
		<slot name="title"
			><h1 class="font-bold p-4 bg-zinc-900 text-white"><!-- optional fallback --></h1></slot
		>
	{/if}
	<slot name="content">
		<p>No content provided</p>
	</slot>
	<div
		role="presentation"
		on:mouseenter={() => {
			hover = true;
		}}
		on:mouseleave={() => {
			hover = false;
		}}
	>
		<slot name="cta" {hover}>
			<button on:click|self>Close modal</button>
		</slot>
	</div>
</div>
<div class="modal-backdrop" />

<style>
	.modal {
		position: relative;
		margin: 2rem;
		background-color: #fff;
		z-index: 2;
	}
	.modal-backdrop {
		position: fixed;
		background-color: rgba(0, 0, 0, 0.7);
		top: 0;
		right: 0;
		bottom: 0;
		left: 0;
		z-index: 1;
	}
</style>
