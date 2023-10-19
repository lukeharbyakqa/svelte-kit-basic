<script>
	let searchedValue = '';
	let checked = false;
</script>

<pre>BINDING</pre>
<h3>Searched: {searchedValue}</h3>
<input bind:value={searchedValue} type="text" id="textInput" />

<h3>Checked: {checked}</h3>
<input type="checkbox" name="" id="" bind:checked />
