<script>
	let head = ""
	let answer = ""
	let points = 0
	let question = 0
	let questions = [
		["Vad heter hund på franska", "chien"],
		["Vad heter vår programmering lärare", "einar"],
		["Vilken frukt är grön", "päron"],
		["Vilket år blev stefan löven stadsminister", "2018"],
		["Vilken är Kanye west mest streamade låt", "Stronger"]
	]
	

	function checkAnswer() {
		if (answer.toLowerCase() == questions[question][1]) {
			points = points + 1
			question = question + 1
			answer = ""
		} else {
			question = question + 1
			answer = ""
		}

		if (question > 4) {
			head = "du är klar"
		}

		console.log(questions[question][1])
		console.log("nu körs checkAnswer")
		return head
	}
	
</script>

<main>
	<h1>{questions[question][0]}?!</h1>
	<p>{points}</p>
	<button on:click={checkAnswer}>Check answer</button>
	<input type="text" bind:value={answer}>
	<h1>{head}</h1>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #00ff4c;
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