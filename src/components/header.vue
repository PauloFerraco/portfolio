<template>
	<header class="header">
		<NavBar/>
		<div class="content header-content" data-aos="slide-up">
			<div class="name">
				<div class="logo-extends">
					<span class="blue">&#10094;</span>
					<strong>Paulo</strong>
					<span class="light">Ferraço</span>
					<span class="blue">/&#10095;</span>
				</div>
				<div class="text" id="text">
					<span>Sou apaixonado em soluções digitais e inovadoras, combinando minhas</span><br>
					<span class="two">habilidades tanto no Front-end quanto em Back-end.</span>
				</div>
			</div>
			<div class="buttons">
				<a href="https://github.com/PauloFerraco" target="_blank" rel="noopener noreferrer external">
					<button class="btn1"><i class="fa-brands fa-github"></i></button>
				</a>
				<a href="https://www.linkedin.com/in/paulo-cesar-ferra%C3%A7o-13a9561b9/" target="_blank" rel="noopener noreferrer external">
					<button class="btn2"><i class="fa-brands fa-linkedin"></i></button>
				</a>
			</div>
			<div class="cursor"></div>
		</div>
	</header>
</template>

<script>
import NavBar from './navbar.vue'
import ScrollReveal from 'scrollreveal'

export default {
	name: 'HeaderMain',
	components: {
		NavBar,
	},
	methods:{
	},
	mounted(){
		ScrollReveal().reveal('.btn1', {
			reset:true,
			origin: 'right',
			distance: '80px',
			delay: 200,
			easing: 'ease-in'
		})
		ScrollReveal().reveal('.btn2', {
			reset:true,
			origin: 'right',
			distance: '80px',
			delay: 400,
			easing: 'ease-in'
		})
		ScrollReveal().reveal('.logo-extends', {
			scale: 1.6
		})
		
	}
}
</script>

<style scoped>
.header {
	position: relative;
	width: var(--width);
	height: 100vh;
	display: flex;
	justify-content: center;
}

.header .content {
	width: 100%;
	height: 100vh;
	display: flex;
	justify-content: space-between;
	align-items: center;
}

.content .name {
	width: 50%;
}

.name .text {margin-left: 15px;user-select: none;}

.name .text span {
	position: relative;
	width: 100%;
	height: 40px;
	line-height: 20px;
	font-weight: normal;
	font-size: 15px;
	color: var(--font);
	overflow: hidden;
	white-space: nowrap;
	z-index: 0;
}
/* .name .text span.two {animation: degrade 4s steps(60) 4.2s normal;} */

.name .text span::after {
	content: '';
	position: absolute;
	width: calc(100% + 8px);
	height: 100%;
	left: 0;
	top: 0;
	animation: degrade 3s normal;
	z-index: 1;
}

.name .text::before {
	content: '';
	position: absolute;
	display: inline-block;
	background-color: var(--blue);
	margin: 0px 0 0 -15px;
	height: 40px;
	width: 2px;
}
/* .name .text span.two:after{
	content: '';
	position: absolute;
	display: inline-block;
	background-color: var(--blue);
	margin: -2px 0 0 2px;
	height: 25px;
	width: 2px;
	animation: cursor 1.8s infinite;
} */

@keyframes cursor {
	0% { opacity: 0; }
	50% { opacity: 1; }
	100% { opacity: 0; }
}

@keyframes letras {
	0% {width: 0;}
	100% {width: 100%;}
}

@keyframes degrade {
	0% {box-shadow: -500px 0px 8px 0px var(--body) inset;}
	80% {box-shadow: -8px 0px 8px 0px var(--body) inset;}
}

.name .logo-extends {
	position: relative;
	width: 100%;
	height: 80px;
	/* background-image: url('../assets/logo-extends.png'); */
	background-repeat: no-repeat;
	background-position: 0 center;
	font-size: 36px;
	color: #fff;
	user-select: none;
	overflow: hidden;
	animation: letras 3.5s steps(40) normal;
}
.name .logo-extends.active {animation: letras 3.5s steps(40) normal;}

.name .logo-extends .blue {color: var(--blue); font-family: 'Inter', sans-serif;font-weight: 600;font-size: 30px;}
.name .logo-extends .light {font-family: 'Inter', sans-serif;font-weight: 100;}
.name .logo-extends strong {font-family: 'Anton', sans-serif;}

.buttons {
	width: 30%;
	height: auto;
}

.buttons button {
	width: 250px;
	height: 48px;
	background-color: var(--color2);
	border-radius: 10px;
	font-size: 28px;
	color: #fff;
	margin-top: 16px;
}

.cursor {
	position: absolute;
	bottom: 30px;
	left: 50%;
	width: 24px;
	height: 24px;
	background-image: url('../assets//mouse1.png');
}

@media only screen and (max-width: 500px) {
	header {
		width: 100%;
		overflow: hidden;
	}

	.header .content {
		/* display: block; */
		flex-wrap: wrap;
		justify-content: center;
	}

	.content .name {
		width: 100%;
		padding-left: 10px;
		margin-top: 150px;
		height: 190px;
	}

	.name .logo-extends {
		left: 0px;
		opacity: 1 !important;
	}
	.name .text {
		position: relative;
		left: 0;
	}
	.name .text span {display: block;height: 20px;overflow: inherit;white-space: inherit;}

	.name .text::before {height: 80px;}

	.buttons {
		width: 80%;
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
	}

	.cursor {display: none}
}
</style>