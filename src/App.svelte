<script>
	import ContactCard from "./ContactCard.svelte";

	let name = 'Roni';
	let title = "";
	let image = "";
	let description = "";
	let age = 26;

// $: structure complier that makes sure when we change name it runs the code again
	$: uppercaseName = name.toUpperCase();
	$: console.log(name);
	$: if (name === 'Veronica') {
		age = 31;
	}

	function incrementAge() {
		age += 1;
	}

	function changeName() {
		name = 'Veronica';
	}

	function nameInput(event) {
		const enteredValue = event.target.value;
		name = enteredValue;
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {uppercaseName}, my age is {age}</h1>
<button on:click={incrementAge}>Change Age</button>
<!-- <button on:click={changeName}>Change Name</button> -->
<!-- <input type="text" value={name} on:input={nameInput}> -->
<!-- shortcut: -->
<input type="text" bind:value={name}  />
<input type="text" bind:value={title} />
<input type="text" bind:value={image} />
<textarea rows="3" bind:value={description} />

<ContactCard 
userName={name}
jobTitle={title} 
description={description}
userImage={image}
/>