<template>
	<div class="header-top" :class="{'active': posScroll > 20}" >
		<div class="center">
			<div class="logo"></div>
			<div class="bars" @click="nav = !nav"><i class="fa-solid " :class="{'fa-bars': nav == false, 'fa-xmark': nav == true}"></i></div>
			<nav :class="{'active': nav == true}">
				<ul>
					<li :class="{ 'active': posScroll >= 0 && posScroll <= 944}"><p @click="to('.header', $event), nav = false">Início</p></li>
					<li :class="{ 'active': posScroll >= 945 && posScroll <= 1889}"><p @click="to('.sobre', $event), nav = false">Sobre mim</p></li>
					<li :class="{ 'active': posScroll >= 1890 && posScroll <= 2834}" @click="to('.tecn', $event), nav = false"><p>Conhecimentos</p></li>
					<li :class="{ 'active': posScroll >= 2835 && posScroll <= 3779}"><p  @click="to('.proj', $event), nav = false">Projetos</p></li>
					<li :class="{ 'active': posScroll >= 3780}"><p  @click="to('.contato', $event), nav = false">Contatos</p></li>
					<li><p><a href="http://api.pauloferraco.com.br" target="_blank" rel="noopener noreferrer">API</a></p></li>
				</ul>
			</nav>
		</div>
   </div>
</template>

<script>
	export default {
		name: 'NavBar',
		data() {
			return {
				click: false,
				posScroll: 0,
				nav: false
			}
		},
		methods:{
			to(el){
				document.querySelector(el).scrollIntoView({ block: "start", behavior: "smooth" })
			}
		},
		mounted(){
			addEventListener('scroll', () => {
				this.posScroll = window.scrollY
				// console.log(window.scrollY);
			})
		}
	}
</script>

<style scoped>

.header-top {
	position: fixed;
	width: 100%;
	height: 120px;
	z-index: 99;
}
.header-top.active {
	box-shadow: 0 2px 5px rgba(0,0,0,.2);
	background-color: rgba(0,0,0,.4);
}

.header-top .center {
	position: relative;
	width: var(--width);
	height: 100%;
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin: 0 auto;
}

.header-top .logo {
	width: 60px;
	height: 60px;
	background-image: url('../assets/logo-small.png');
	background-repeat: no-repeat;
}

.header-top nav {
	width: 50%;
	height: 100%;
}

.header-top ul {
	width: 100%;
	height: 100%;
	display: flex;
	justify-content: space-between;
	align-items: center;
}

.header-top ul li{transition: all .4s ease-in-out;height: 100%;display: flex;align-items: center;}

.header-top ul li p {
	width: 100%;
	height: 20px;
	font-size: 16px;
	font-weight: 500;
	line-height: 20px;
	color: var(--font);
	user-select: none;
	text-align: center;
	padding: 0 10px;
	cursor: pointer;
	transition: all .3s ease-in-out;
}
.header-top ul li:hover,
.header-top ul li.active {box-shadow: 0 -3px 0px 0px var(--blue) inset;}

.header-top .bars {display: none;}

@media only screen and (max-width: 500px) {

	.header-top .bars {
		position: absolute;
		right: 20px;
		top: 30px;
		width: 60px;
		height: 60px;
		font-size: 20px;
		color: var(--font);
		text-align: center;
		line-height: 60px;
		display: block;
		/* background-color: #303030; */
		border-radius: 6px;
		transition: all .3s ease;
	}

	.header-top nav {display: none; overflow: hidden;}
	.header-top nav.active {
		position: absolute;
		display: block;
		top: 120px;
		left: 0;
		width: 100%;
		height: calc(100vh - 100px);
		background-color: var(--body);
		border-top: 2px solid #303030;
		z-index: 99;
	}
	.header-top ul li:hover, .header-top ul li.active {box-shadow: none;}

	.header-top nav.active ul {
		width: 100%;
		height: auto;
		justify-content: center;
		flex-wrap: wrap;
	}
	.header-top nav.active ul li {
		width: 100%;
		height: 80px;
		display: block;
	}
	
	.header-top nav.active ul li p {
		width: 100%;
		line-height: 76px;
		overflow: inherit;
	}
	
	.header-top {width: 100%;}
	
	.header-top .center {width: 100%;justify-content: center;}

	.header-top nav {width: 80%;justify-content: center;}

	.header-top nav ul li p {width: 80px; overflow: hidden; white-space: nowrap;text-overflow: ellipsis;}
}
</style>