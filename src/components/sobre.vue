<template>
	<section class="sobre" data-aos="fade-in">
		<div class="logo logo-sobre"></div>
		<div class="text text-sobre">
			Olá! Sou Paulo Ferraço, desenvolvedor Front-end quanto em Back-end. Com anos de experiência prática, 
			sou apaixonado por transformar ideias em soluções funcionais e inovadoras.
			<br><br>
			Minha jornada no mundo do desenvolvimento começou com minha fascinação por tecnologia e minha curiosidade em entender como as 
			coisas funcionam nos bastidores. Ao longo dos anos, aprimorei minhas habilidades em diversas áreas, adquirindo um conhecimento profundo em linguagens de programação, 
			frameworks e tecnologias relevantes.
			<br><br>
			Neste portfólio, você encontrará exemplos dos projetos nos quais trabalhei, destacando minhas habilidades e conquistas. 
			Estou sempre em busca de novos desafios e oportunidades para expandir meus conhecimentos e enfrentar problemas complexos de forma criativa e eficiente.
		</div>
	</section>
</template>

<script>
// import { gsap } from 'gsap';
import ScrollReveal from 'scrollreveal'

export default {
	name: 'SobreMim',
	methods:{
	},
	mounted(){
		ScrollReveal().reveal('.logo-sobre', {delay: 200, reset: true,duration: 1000, origin: 'left', distance: '100px' });
		ScrollReveal().reveal('.text-sobre', {delay: 200, reset: true,duration: 1000, origin: 'right', distance: '100px' });
	}
}
</script>

<style scoped>

.sobre {
	width: var(--width);
	height: 100vh;
	display: flex;
	justify-content: space-evenly;
	align-items: center;
}

.sobre .logo {
	width: 40%;
	height: 250px;
	background-image: url('../assets/logo-grand.png');
	background-repeat: no-repeat;
	background-position: center;
	background-size: contain;
}

.sobre .text {
	width: 50%;
	height: auto;
	background-color: var(--color2);
	padding: 16px;
	border-radius: 10px;
	color: var(--font);
	font-size: 14px;
	font-weight: 500;
}

@media only screen and (max-width: 500px) {
	.sobre .text {width: 90%;}
	.sobre .logo {height: 120px;}
}
</style>