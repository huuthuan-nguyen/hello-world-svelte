<script>
	import ContactCard from "./ContactCard.svelte";

	let name = "Max";
	let age = 30;
	let title;
	let description;
	let image;

	$: uppercaseName = name.toUpperCase();

	function incrementAge() {
		age += 1;
	}

	function changeName() {
		name = "Thuan Nguyen";
	}
	function nameInput(event) {
		const enteredValue = event.target.value;
		name = enteredValue;
	}
</script>

<h1>Hello {uppercaseName}, my age is {age + 1}!</h1>
<button on:click={incrementAge}>Change Age</button>
<!-- <button on:click={changeName}>Change Name</button> -->
<!-- <input type="text" value={name} on:input={nameInput}/> -->
<input type="text" bind:value={name} />
<input type="text" bind:value={title} />
<input type="text" bind:value={image} />
<textarea bind:value={description}></textarea>

<ContactCard userName={name} jobTitle={title} {description} userImage={image} />

<style>
	h1 {
		color: purple;
	}
</style>
