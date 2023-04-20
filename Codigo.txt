<!DOCTYPE html>
<html>
<head>
	<title>Bet do Leminha</title>
	<style>
		body {
			font-family: Comic, sans-serif;
		}
		h1 {
			text-align: center;
			margin-top: 30px;
		}
		form {
			display: flex;
			flex-direction: column;
			align-items: center;
			margin-top: 50px;
		}
		input {
			margin: 10px;
			padding: 5px;
			width: 50px;
			text-align: center;
		}
		button {
			margin-top: 20px;
			padding: 10px;
			background-color: #f10f07;
			color: rgb(0, 0, 0);
			border: none;
			border-radius: 5px;
			cursor: pointer;
		}
		#result {
			margin-top: 30px;
			font-weight: bold;
			font-size: 20px;
			text-align: center;
		}
	</style>
</head>
<body>
	<h1>Bet do Leminha</h1>
    <p id="result">Arrisque sua sorte entre 0x0 até 10x10</p>
	<form>
		<label for="time-casa">Palmeiras:</label>
		<input type="number" id="time-casa" min="0">
		<label for="time-visitante">Corinthians:</label>
		<input type="number" id="time-visitante" min="0">
		<button type="submit">Enviar</button>
	</form>
	<div id="result"></div>
	<script>
var resultado = {
	timeCasa: 2,
	timeVisitante: 1
};
function verificarPalpites(palpiteCasa, palpiteVisitante) {
	if (palpiteCasa == resultado.timeCasa && palpiteVisitante == resultado.timeVisitante) {
		return true;
	} else {
		return false;
	}
}
function mostrarResultado(acertou) {
	var resultadoDiv = document.getElementById("result");
	if (acertou) {
		resultadoDiv.innerHTML = "Ganhou, pode respirar gratuitamente";
		resultadoDiv.style.color = "#4CAF50";
	} else {
		resultadoDiv.innerHTML = "Errouuuu.";
		resultadoDiv.style.color = "#f44336";
	}
}
var form = document.querySelector("form");
form.addEventListener("submit", function(event) {
	event.preventDefault();
	var palpiteCasa = parseInt(document.getElementById("time-casa").value);
	var palpiteVisitante = parseInt(document.getElementById("time-visitante").value);
	var acertou = verificarPalpites(palpiteCasa, palpiteVisitante);
	mostrarResultado(acertou);
});

    </script>
</body>
</html>
