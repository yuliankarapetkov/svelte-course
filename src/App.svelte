<script>
	export let name = 'Yulian';
	export let age = 28;

	function incrementAge() {
		age++;
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello my name's {name}, and I'm {age}.</h1>

<button on:click="{incrementAge}">Increment age</button>
