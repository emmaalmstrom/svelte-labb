<script>
	let gron = "#00ff4c"
	let head = ""
	let answer = ""
	let points = 0
	let question = 0
	let questions = [
		["Vad heter hund på franska", "chien"],
		["Vilken slags cancer hade Walter White", "lungcancer"],
		["Vad är första ingredigensen i majonäs", "rapsolja"],
		["Vilken är Kanye west mest streamade låt", "stronger"],
		["Vad heter världens bästa lärare", "einar"],
		["Bra jobbat"]
	]
	

	function checkAnswer() {
		if (answer.toLowerCase() == questions[question][1]) {
			points = points + 1
			question = question + 1
			answer = ""
			document.getElementById("titel").style.backgroundColor = "green";
		} else {
			question = question + 1
			answer = ""
			document.getElementById("titel").style.backgroundColor = "red";
		}

		if (question > 4) {
			if (points == 5) {
				head = "Du fick 5/5 rätt, shit va allmänbildad du är!"
			} else {
				head = "Du fick " + points + "/5 rätt, du har förbättringspotential!"
			}
		}

		console.log(questions[question][1])
		console.log("nu körs checkAnswer")
		return head
	}
	
</script>

<main>
	<h1 id="titel">{questions[question][0]}?!</h1>
	<input type="text" bind:value={answer}>
	<button on:click={checkAnswer}>Check answer</button>
	<p>{points}</p>
	<h1>{head}</h1>
</main>

<style>

	
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
		background-image: linear-gradient(rgb(255, 0, 255), yellow);
		height: 100%;
	}

	h1 {
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
		font-size: 70px;
	}
	button {
		border-radius: 100px;
		width: 150px;
	}
	
	p {
		font-size: 30px;
	}

	input {
		width: 150px;
		border-radius: 100px;
	}


	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>