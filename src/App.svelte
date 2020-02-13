<script>
	let name = 'vero';
	let age = 26;

	function incrementAge() {
		age += 1;
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {name}, my age is {age}</h1>
<button on:click={incrementAge}>Change Age</button>