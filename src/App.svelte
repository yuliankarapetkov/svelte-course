<script>
	let name = 'Yulian';
	let age = 28;

	$: uppercaseName = name.toUpperCase();

	$: console.log(name);

	$: if (name === 'Yulian Karapetkov') {
		age = 25;
	}

	function incrementAge() {
		age++;
	}

	function changeName() {
		name = 'Yulian Karapetkov';
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello my name's {uppercaseName}, and I'm {age}.</h1>

<button on:click="{incrementAge}">Increment age</button>
<!-- <button on:click="{changeName}">Change name</button> -->

<input type="text" bind:value="{name}" />
