<script>
	//import { Svrollbar } from 'svrollbar'
	import 'bootstrap/dist/css/bootstrap.min.css';
	import { quintOut } from 'svelte/easing';
	import { fade, draw, fly } from 'svelte/transition';
	import { expand } from './custom-transitions.js';
	import { outer, left, right, middleSquare } from './shape.js';
	
	import { onMount } from 'svelte';

	let ready = false;
	onMount(() => ready = true);
	
	var style = document.createElement("style");
	style.innerHTML = `body::-webkit-scrollbar {display: none;}`;
	document.head.appendChild(style);

	window.onscroll = function() {myFunction()};

	function myFunction() {
		var winScroll = document.body.scrollTop || document.documentElement.scrollTop;
		var height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
		var scrolled = (winScroll / height) * 100;
		document.getElementById("myBar").style.width = scrolled + "%";
	}

</script>

<svelte:head>
	<!-- <link href="https://fonts.googleapis.com/css?family=Montserrat" rel="stylesheet"> -->

	<style>
		body{
			background: black;
		}
	</style>
</svelte:head>

<main>

	<nav class="navbar">
		<div class="top-container">
			<ul>
				<li><a href="#home">Inicio</a></li>
				<li><a href="#problem">El problema</a></li>
				<li><a href="#solution">La Solución</a></li>
				<li><a href="https://exusai.github.io/Portfolio/">Otros proyectos</a></li>
			</ul>
			<div class="progress-container">
				<div class="progress-bar" id="myBar"></div>
			</div>
		</div>
	</nav>
	

	<section id="home">
		<div class="row align-items-center">
			<div class="col-sm">
				<div class = "centered">
					<h1><span id="w1">a</span><span id="w2">-</span><span id="w3">qua</span></h1>
					<p class="lead">Una solución (hipotética) para la reciente escasez de agua en la Ciudad de México y todo lo que esto implica.</p>
				</div>
			</div>
			<div class="col-sm">
				<div class="centered">
					<span id="logo">
						{#if ready}
							<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 192 192" x="0px" y="0px">
								<g out:fade="{{duration: 200}}" opacity=1>
									<path
										in:expand="{{duration: 500, delay: 1300, easing: quintOut}}"
										style="stroke: #ffffff; fill: #ffffff; fill-opacity: 1.0; stroke-width: 1.5;"
										d={outer}
									/>
									<path
										in:draw="{{duration: 1000, delay: 600}}"
										style="stroke:#ffffff; fill: #4287f5; fill-opacity: 0.0; stroke-width: 1.5"
										d={left}
									/>
									<path
										in:draw="{{duration: 1000, delay: 300}}"
										style="stroke:#ffffff; fill: #4287f5; fill-opacity: 0.0; stroke-width: 1.5"
										d={right}
									/>

									<path
										in:draw="{{duration: 1000}}"
										style="stroke: #ffffff; fill: #4287f5; fill-opacity: 0.0; stroke-width: 1.5"
										d={middleSquare}
									/>
									<path
									in:expand="{{duration: 500, delay: 1500, easing: quintOut}}"
										style="stroke:#ffffff; fill: #4287f5; fill-opacity: 0.8; stroke-width: 1.5"
										d={left}
									/>
									<path
									in:expand="{{duration: 500, delay: 1500, easing: quintOut}}"
										style="stroke:#ffffff; fill: #4287f5; fill-opacity: 0.8; stroke-width: 1.5"
										d={right}
									/>
									<path
										in:expand="{{duration: 500, delay: 1500, easing: quintOut}}"
										style="stroke: #ffffff; fill: #4287f5; fill-opacity: 0.8; stroke-width: 1.5"
										d={middleSquare}
									/>
								</g>
							</svg>
						{/if}
					</span>
				</div>
			</div>
		</div>
	</section>

	<section id="problem">
		<div class="row align-items-center">
			<div class="col-sm">
				<img src="https://github.com/Exusai/a-qua/raw/master/imgs/Mapa.png" alt="Mapa">
			</div>
			<div class="col-sm">
				<h2><span id="w1">El </span><span id="w2">problema</span></h2>
				<p class="lead">Como todos sabemos, la Ciudad de México se encuentra sobre lo que solía ser el lago de Texcoco. Sin embargo, el lago se ha secado durante los últimos 500 años. Y para abastecerce de agua, la Ciudad ha recurrido a los acuiferos debajo de la misma, causando otro problema.</p>
			</div>
		</div>
	</section>

	<section>
		<div class="row align-items-center">
			<div class="col-sm">
				<h3><span id="w1">Hundimiento</span></h3>
				<p class="lead">Como consecuencia de la explotación de los mantos acuiferos, la Ciudad de México se hunde constantemente. En algunas partes, la ciudad se hunde hasta 0.5 metros anualmente y gracias a la plancha de asfalto que cubre la ciudad no se puede reintegrar el agua de la lluvias a los mantos acuiferos.</p>
			</div>
			<div class="col-sm">
				<img src="https://github.com/Exusai/a-qua/raw/master/imgs/hundimiento.png" alt="Hundimiento en la ciudad">
			</div>
		</div>
	</section>

	<section>
		<div class="row align-items-center">
			<div class="col-sm">
				<img src="https://github.com/Exusai/a-qua/raw/master/imgs/hundimiento2.png" alt="Hundimiento ejemplo 2">
			</div>
			<div class="col-sm">
				<!-- <h3><span id="w1">Hundimiento</span></h3> -->
				<p class="lead">Muchos geólogos estiman que para finales del siglo, la Ciudad se habrá hundido entre 20 y 30 metros de donde se encuentra actualmente.</p>
				<!-- <p class="lead"></p> -->
			</div>
		</div>
	</section>

	<section>
		<div class="row align-items-center">
			<div class="col-sm">
				<h3><span id="w1">Escasez </span><span id="w2">de </span><span id="w3">agua</span></h3>
				<p class="lead">Debido a que la Ciudad no puede seguir extrayendo agua de su subsuelo esta importa el 40% de su suminstro de agua a través de un sistema de canales y tuberías.</p>
			</div>
			<div class="col-sm">
				img
			</div>
		</div>
	</section>

	<section>
		<div class="row align-items-center">
			<div class="col-sm">
				img
			</div>
			<div class="col-sm">
				<p class="lead">Este sistema de canales es tan ineficiente que de cada litro de agua bombeado por el mismo, se estima que más de un tercio se pierde en el transporte. Sin mencionar que el hundimiento de la Ciudad causa que las tuberías se rompan constantemente.</p>
			</div>
		</div>
	</section>

	<section>
		<div class="row align-items-center">
			<div class="col-sm">
				<h3><span id="w1">Energía</span></h3>
				<p class="lead">Al tener que importar tanta agua, la Ciudad de México utiliza tanta energía como la Ciudad de Puebla SOLAMENTE para bombear agua. Esto es debido a que el agua debe ser bombeada desde zonas menos elevadas que la ciudad.</p>
			</div>
			<div class="col-sm">
				img
			</div>
		</div>
	</section>

	<section>
		<div class="row align-items-center">
			<div class="col-sm">
				img
			</div>
			<div class="col-sm">
				<p class="lead">Por esta razón la ciudad sufre de tanta escasez de agua como si se encontrase en un desierto, a pesar de que recive incluso más lluvia que Londres.</p>
			</div>
		</div>
	</section>

	<section id="solution">
		<div class="row align-items-center">
			<div class="col-sm">
				<h2><span id="w1">Solución</span></h2>
				<p class="lead">La solución que se propone consta de diversos sistemas distribuidos y aplicados por toda la ciudad. Estos estarían basados en el Computo en la Nube, IoT, Machine Learning y Big Data.</p>
			</div>
			<div class="col-sm">
				img
			</div>
		</div>
	</section>

	<section>
		<div class="row align-items-center">
			<div class="col-sm">
				<h3><span id="w1">Recolección </span><span id="w2">de </span><span id="w3">agua</span></h3>
				<p class="lead">Se proponen diversos sitemas inteligentes de recolección de agua en las calles y edificios, los cules sean capaces de reingresar agua a los sistemas subterraneos o de abastecer a su respectivo edificio dependiedo de lo que la "nube" determine que sea más necesario.</p>
			</div>
			<div class="col-sm">
				img
			</div>
		</div>
	</section>

	<section>
		<div class="row align-items-center">
			<div class="col-sm">
				<h3><span id="w1">Reducir </span><span id="w2">desperdicio de </span><span id="w3">agua</span></h3>
				<p class="lead">Se sabe que una porción importante del agua desperdiciada es causada por infraestructura deficiente en casas y edificios. Para abordar este problema se rediseñaría esta misma infraestructura pero con IoT y conección a la nube, de modo que las fugas puedan ser detectadas y reparadas lo más pronto posible.</p>
			</div>
			<div class="col-sm">
				img
			</div>
		</div>
	</section>

	<section>
		<div class="row align-items-center">
			<div class="col-sm">
				<h3><span id="w1">Distribución </span><span id="w2">de </span><span id="w3">agua</span></h3>
				<p class="lead">De manera similar a las redes de distribución de energía de las ciudades inteligentes, la propuesta es tener una red que distribuya el agua en función de donde se necesita más o donde puede ser almacenada si es que no se necesita.</p>
			</div>
			<div class="col-sm">
				img
			</div>
		</div>
	</section>

	<section>
		<h1><span id="w1">Acerca </span><span id="w2">de esta </span><span id="w3">página</span></h1>
	</section>

	<!-- <section>
		<div class="row align-items-center">
			<div class="col-sm">
				<h3><span id="w1">Almacenamiento </span><span id="w2">de </span><span id="w3">agua</span></h3>
				<p class="lead">wea</p>
			</div>
			<div class="col-sm">
				img
			</div>
		</div>
	</section> -->

</main>



<style>
	* {
		margin: 0;
		padding: 0;
	}
	
	:-webkit-scrollbar { display: none; }
	:root{
		background: black;
		color: #fff;
		/* height: 100vh;
		width: 100vh; */
		line-height: 1.6;
		overflow: hidden;

		-ms-overflow-style: none;  /* IE and Edge */
		scrollbar-width: none;     /* Firefox */
		
		width: 100%;
		height: 100%;
		/* CSS Smooth Scroll */
		overflow-y: scroll; 
		scroll-behavior: smooth;
		scroll-snap-type: y mandatory;

		font-family: 'Roboto';
		
	}

	@import url('https://fonts.googleapis.com/css?family=Roboto&display=swap');

	h1 #w1 {
		animation: fade2 2s infinite;
		animation-fill-mode: both;
		animation-delay: .7s;
	}
	h1 #w2 {
		animation: fade2 2s infinite;
		animation-fill-mode: both;
		animation-delay: 1.2s;
	}
	h1 #w3 {
		animation: fade2 2s infinite;
		animation-fill-mode: both;
		animation-delay: 1.7s;
	}

	h2 #w1 {
		animation: fade2 2s infinite;
		animation-fill-mode: both;
		animation-delay: .7s;
	}
	h2 #w2 {
		animation: fade2 2s infinite;
		animation-fill-mode: both;
		animation-delay: 1.2s;
	}
	h2 #w3 {
		animation: fade2 2s infinite;
		animation-fill-mode: both;
		animation-delay: 1.7s;
	}

	h3 #w1 {
		animation: fade2 2s infinite;
		animation-fill-mode: both;
		animation-delay: .7s;
	}
	h3 #w2 {
		animation: fade2 2s infinite;
		animation-fill-mode: both;
		animation-delay: 1.2s;
	}
	h3 #w3 {
		animation: fade2 2s infinite;
		animation-fill-mode: both;
		animation-delay: 1.7s;
	}

	@keyframes fade {  
		0% {
			opacity: 0;
		}
		50% {
			opacity: 1;
		}
		100% {
			opacity: 0;
		}
	}

	@keyframes fadeIn {  
		0% {
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}

	@keyframes fade2 {
		0% {
			opacity: .7;
		}
		50% {
			opacity: 1;
		}
		100% {
			opacity: .7;
		}
	}

	@keyframes fade3 {
		0% {
			opacity: .8;
		}
		50% {
			opacity: 1;
		}
		100% {
			opacity: .8
		}
	}
	
	.centered #logo{
		left: 50%;
		top: 50%;

		animation: fade3 5s infinite;
		animation-fill-mode: both;
		animation-delay: 1.5s;
	}

	.top-container {
		position: fixed;
		z-index: 1;
		width: 100%;
		background: rgba(0,0,0,0);
		top: 0;
	}

	/* The progress container (grey background) */
	.progress-container {
		width: 100%;
		height: 8px;
		background:rgba(204,204,204,.7);
	}

	/* The progress bar (scroll indicator) */
	.progress-bar {
		height: 8px;
		background: skyblue;
		width: 0%;
	}

	.lead {
		font-size: 1.5rem;
	}

	.navbar {
		position: fixed;
		top: 0;
		left: 0;
		z-index: 2;
		display: flex;
		width: 100%;
		height: 60px;
		background: rgba(0,0,0,0.7);
	}

	.navbar ul {
		display: flex;
		list-style: none;
		width: 100%;
		justify-content: center;
	}

	.navbar ul li {
		margin: 0 1rem;
		padding: 1rem;
	}

	.navbar ul li a {
		text-decoration: none;
		text-transform: uppercase;
		color: #f4f4f4;
	}

	.navbar ul li a:hover {
		color: skyblue;
	}

	section {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		text-align: center;
		width: 100%;
		height: 100vh;
		color:#fff;
		background-color: black;
		/* Scroll Snap */
		scroll-snap-align: center;
		animation: fadeIn 2s;
	}

	section h1 {
		font-size: 4rem;
	}

	/* Section Images */
	section#home {
		margin: 0;
		padding: 0;
		background: url('https://github.com/Exusai/a-qua/raw/master/imgs/BG1.png') no-repeat center center/cover;;	
	}

	section#about {
		margin: 0;
		padding: 0;
		background: black;
	}

	section#servicio {
		margin: 0;
		padding: 0;
		background: url('https://source.unsplash.com/K2tdx2mFDHc/1600x900') no-repeat center center/cover;;
	}

	/* section#contact {
		margin: 0;
		padding: 0;
		background: url('https://source.unsplash.com/2aAHlfDOhJM/1600x900') no-repeat center center/cover;;
	} */

</style>