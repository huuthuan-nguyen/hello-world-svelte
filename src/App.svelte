<script>
	let name = 'Max';
	let age = 30;

	$: uppercaseName = name.toUpperCase();

	function incrementAge() {
		age += 1;
	}

	function changeName() {
		name = 'Thuan Nguyen';
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

<h1>Hello {uppercaseName}, my age is {age + 1}!</h1>
<button on:click="{incrementAge}">Change Age</button>
<!-- <button on:click={changeName}>Change Name</button> -->
<input type="text" value={name} on:input={nameInput}/>