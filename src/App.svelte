<script>
		const shuffleArray = array => 
{

  for (let i = array.length - 1; i > 0; i--) 
  {
    const j = Math.floor(Math.random() * (i + 1));
    const temp = array[i];
    array[i] = array[j];
    array[j] = temp;
  }
  
}
		let gameState = { started: false };
		let protip = ["No dudes nunca del resultado final, y disfruta el proceso.","Los lugares que tengo el placer de conocer gracias a los negocios digitales.",
									"Pensar que el año pasado nunca me imaginé que podría estar en un hotel 5 P y encima para trabajar. Hoy si puedo decir que disfruto 100% de mi tiempo.","Para dar en el blanco, apunta mas alto.",
									"Toda persona exitosa, es alguien que fracasó pero que no se consideró un fracasado.","Viajar, disfrutar, ser feliz y sobre todas las cosas, agradecer todo lo que tenemos=",
								 "La vida no cambia por cuestiones de suerte, se trata de tomar decisiones.Gracias a una decisión que tomé hace casi cinco meses, hoy estoy teniendo resultados muy diferentes a los que tenía antes.",
								 "Si empezaste algo nuevo hace poco, puede que ahora no estás donde queres, pero seguro no estás donde estabas cuando comenzaste.",
								 `Tu mundo exterior solo es un reflejo de tu "mundo interior."`]

	function startGame() {
		gameState.started = !gameState.started;
	}
</script>

<body>
	{#if gameState.started}
	<div class="inicio">
	<header>
		<h1>
			El Boss - The Game
		</h1>
		<h2>
			Querés llevar tu vida al proximo nivel?
		</h2>
	</header>
	<main>
		<button class="inicio" on:click={startGame}>
			press start
		</button>
	</main>
	<footer>
	</footer>
		</div>
	{:else}
	<main>
		<div class="gameover">
		<h2>
			llevaste tu vida al proximo nivel
		</h2>
		<button class="reinicio" on:click={startGame} on:click={shuffleArray(protip)}>
			reiniciar
		</button>
		<p>
			protip: {protip[0]}
		</p>	
			</div>
	</main>
	{/if}
</body>
<style>
	body{
		background-image:url("https://static.coindesk.com/wp-content/uploads/2018/08/etcrbcb-scaled.jpg")
	}
	header,
	main{
		font-family: monospace;
		font-size: 3rem;
		text-align: center;
		color: white;
	}
	button.reinicio{
		background:rgba(255,220,100,.8);
		backdrop-filter: blur(10px);
	}
	button.reinicio:hover{
		background:rgba(35,220,30,.8);
		transition:.1s;
	}
	button.inicio{
		background:rgba(255,220,100,.4);
		backdrop-filter: blur(10px);
	}
	button.inicio:hover{
		background:rgba(35,220,30,.4);
		transition:.1s;
	}
	div.inicio{
		background:rgba(255,220,100,.4);
		backdrop-filter: blur(10px);
		box-shadow: 20px;
	}
		div.gameover{
		background:rgba(255,20,20,.4);
		backdrop-filter: blur(10px);
		box-shadow: 20px;
	}
</style>