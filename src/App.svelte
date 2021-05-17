<script>
	export let name;
	let secretWord = ""
	let age = 17

	function levelUp() {
		if (age < 30) {
			age = age + 1
		}
	}
</script>

<main>
	<h1>Hello {secretWord}!</h1>
	<p>{age}</p>
	<button on:click={levelUp}>level up</button>
	<input type="password" bind:value={secretWord}>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>