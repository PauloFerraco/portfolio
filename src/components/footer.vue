<template>
	<footer>
		<div class="center">
			<div class="about"><span>Pauloferraco.com.br</span> &copy; 2023 - Todos os direitos reservados.</div>
			<div class="logo"></div>
		</div>
	</footer>
</template>

<script>
	export default {
		name: 'FooterItem',
	}
</script>

<style scoped>

footer {
	width: 100%;
	height: 100px;
	background-color: #1B1B1B;
	display: flex;
	justify-content: center;
}

footer .center {
	width: var(--width);
	height: 100%;
	display: flex;
	justify-content: space-between;
	align-items: center;
}

footer .about {
	font-size: 13px;
}

footer .logo {
	width: 350px;
	height: 70px;
	background-image: url('../assets/logo-extends2.png');
	background-repeat: no-repeat;
	background-size: contain;
	transform: scale(.7);
}

@media only screen and (max-width: 500px) {
	footer {
		height: 200px;
	}

	footer .center {
		width: 100%;
		justify-content: center;
		flex-wrap: wrap;
		padding: 0 10px;
	}

	footer .logo {
		width: 100%;
	}
}

</style>