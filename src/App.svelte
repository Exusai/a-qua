<script>
	//import { Svrollbar } from 'svrollbar'
	import 'bootstrap/dist/css/bootstrap.min.css';
	import { quintOut } from 'svelte/easing';
	import { fade, draw, fly } from 'svelte/transition';
	import { expand } from './custom-transitions.js';
	import { inner, outer } from './shape.js';
	
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
	<link href="https://fonts.googleapis.com/css?family=Montserrat" rel="stylesheet">

	<style>
		/* Global CSS via SASS */
		body{
			background: black;
		}
	</style>
</svelte:head>

<main>

	<nav class="navbar">
		<div class="top-container">
			<ul>
				<li><a href="#home">Home</a></li>
				<li><a href="#about">Acerca de</a></li>
				<!-- <li><a href="#servicio">Servicio</a></li> -->
				<li><a href="https://exusai.github.io/Portfolio/">Otros proyectos</a></li>
			</ul>
			<div class="progress-container">
				<div class="progress-bar" id="myBar"></div>
			</div>
		</div>
	</nav>
	

	<section id="home">
		<div class="row">
			<div class="col-sm">
				<h1><span id="w1">a</span><span id="w2">-</span><span id="w3">qua</span></h1>
				<p class="lead">Una solución (hipotética) para la reciente escasez de agua en la Ciudad de México y todo lo que esto implica.</p>
			</div>
			<div class="col-sm">
				<div class = "centered">
					<svg xmlns="/mnt/c/Users/ironm/Desktop/reto01/imgs/Logo.svg" viewBox="0 0 50 50">
						<!-- <g out:fade="{{duration: 200}}" opacity=0.2>
							<path
								in:expand="{{duration: 400, delay: 1000, easing: quintOut}}"
								style="stroke: #ff3e00; fill: #ff3e00; stroke-width: 50;"
								d={outer}
							/>
							<path
								in:draw="{{duration: 1000}}"
								style="stroke:#ff3e00; stroke-width: 1.5"
								d={inner}
							/>
						</g> -->
					</svg>
				
					<!-- <div class="centered" out:fly="{{y: -20, duration: 800}}">
						{#each 'SVELTE' as char, i}
							<span
								in:fade="{{delay: 1000 + i * 150, duration: 800}}"
							>{char}</span>
						{/each}
					</div> -->
				</div>
			</div>
		</div>
	</section>
	<!-- En la ciudad de méxico comienza a escacear el agua -->
	<!-- diagramas del bideo ese -->
	<!-- usar ia para recolectar agua -->
	<!-- usar iot para aumentar la eficiencia de recolectar agua  -->
	<section id="about">
		<div class="row">
			<div class="col-sm">
				imagen pro
			</div>
			<div class="col-sm">
				<h2>El problema</h2>
				<p class="lead">Como todos sabemos, la Ciudad de México se encuentra sobre lo que solía ser el lago de Texcoco.</p>
				<p class="lead">Sin embargo, el lago se ha secado durante los últimos 500 años. Y la Ciudad ha recurrido a los acuiferos debajo de la misma, causando otro problema.</p>
			</div>
		</div>
	</section>

	<section>
		<div class="row">
			<div class="col-sm">
				<h3>Hundimiento</h3>
				<p class="lead">Como consecuencia de la explotación de los mantos acuiferos, la Ciudad de México se hunde constantemente.</p>
				<p class="lead">En algunas partes, la ciudad se hunde hasta 0.5 metros anualmente.</p>
			</div>
			<div class="col-sm">
				Imagen logo bien cool
			</div>
		</div>
	</section>

	<section>
		<div class="row">
			<div class="col-sm">
				img
			</div>
			<div class="col-sm">
				<h3>Escasez de agua</h3>
				<p class="lead">Debido a que la superficie de lo que antes era el lago de Texcoco se encuentra en su mayoría cubierta por concreto, el manto acuifero debajo de la ciudad no puede reabastecerse lo suficiente incluso cuando la Ciudad de México recive más lluvia que ciudades famosas por recibir lluvia durante todo el año como Londres.</p>
			</div>
		</div>
	</section>

	<!-- al no poder explotar el agua, la ciudad recurre a un ineficiente sistema de canales, pues estos deben elevar el agua primero, y debido al hundimineto de la ciudad estos se rompen contantemnte -->
	<!-- de cada litro bombeado por  estas tuberias, se estima que mas de un tercio se perdera en el transporte -->
	<!-- solución distopica con la nube -->
	<section id="servicio">
		<div class="row">
			<div class="col-sm">
				Imagen bien cool
			</div>
			<div class="col-sm">
				<h3>Energía</h3>
				<p class="lead">La Ciudad de México utiliza tanta energía como toda la Ciudad de Puebla ÚNICAMENTE para abastecerce de al rededor del 40% de su suminstro de agua.</p>
				<!-- <p class="lead">Pero ¿Por qué es esto?</p> -->
			</div>
		</div>
	</section>
	<!-- <section id="contact">
		<h1>Contact</h1>
		<p class="lead">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Commodi, quis!</p>
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
		
	}

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

	.centered {
		left: 50%;
		top: 50%;
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
	}

	section h1 {
		font-size: 4rem;
	}

	/* Section Images */
	section#home {
		margin: 0;
		padding: 0;
		background: url('https://source.unsplash.com/bZZp1PmHI0E/1600x900') no-repeat center center/cover;;
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