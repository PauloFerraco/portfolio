<template>
	<section class="contato">
		<div class="title">Contatos</div>
		<div class="content contats-box">
			<div class="box">
				<div class="icon"><i class="fa-brands fa-github"></i></div>
				<div class="text git">PauloFerraco</div>
				<a href="https://github.com/PauloFerraco" target="_blank" rel="noopener noreferrer external">
					<div class="fontIcon"><i class="fa-solid fa-up-right-from-square"></i></div>
				</a>
			</div>
			<div class="box">
				<div class="icon"><i class="fa-brands fa-linkedin"></i></div>
				<div class="text link">Paulo Ferraço</div>
				<a href="https://www.linkedin.com/in/paulo-cesar-ferra%C3%A7o-13a9561b9/" target="_blank" rel="noopener noreferrer external">
					<div class="fontIcon"><i class="fa-solid fa-up-right-from-square"></i></div>
				</a>
				</div>
			<div class="box">
				<div class="icon"><i class="fa-solid fa-envelope"></i></div>
				<input readonly class="text email" value="contato@pauloferraco.com.br">
				<div class="copy fontIcon" @click="copy(1)"><i class="fa-solid fa-copy"></i></div>
			</div>
			<div class="box">
				<div class="icon"><i class="fa-brands fa-discord"></i></div>
				<input readonly class="text dc" value="Zinii">
				<div class="copy fontIcon" @click="copy(2)"><i class="fa-solid fa-copy"></i></div>
			</div>
		</div>
	</section>
</template>

<script>
import ScrollReveal from 'scrollreveal';

export default {
	name: 'ContatoItem',
	data() {
		return {
			
		}
	},
	methods:{
		copy(n){
			let textArea = ''
			if(n == 1){
				textArea = document.querySelector('.email');
			}else if(n == 2){
				textArea = document.querySelector('.dc');
			}
			// console.log(textArea.select());
			textArea.select();
			document.execCommand('copy');
		}
	},
	mounted(){
		ScrollReveal().reveal('.contats-box', {delay: 200, reset: true,duration: 1000, origin: 'top', distance: '100px' });
	}
}
</script>

<style scoped>
.contato {
	height: calc(100vh - 100px);
}

.contato .content {
	width: 100%;
	height: auto;
	display: flex;
	justify-content: space-evenly;
	flex-wrap: wrap;
}

.content .box {
	width: calc(40% - 10px);
	height: 40px;
	background-color: rgba(0,0,0,.3);
	display: flex;
	justify-content: space-evenly;
	align-items: center;
	margin-top: 6px;
	border-radius: 6px;
	font-size: 14px;
}

.content .box .icon {font-size: 16px;width: 30px;height: 100%; line-height: 40px;text-align: center;}

.content .box input::selection,
.content .box .text::selection { background-color: var(--color2);}

.content .box .copy {cursor: pointer;}

.content .box .text,
.content .box input {
	width: 50%;
	text-align: center;
	font-size: 14px;
	font-weight: 500;
}

.content .box .fontIcon {font-size: 12px;width: 30px;height: 100%; line-height: 40px;text-align: center;}

@media only screen and (max-width: 500px) {

	.contato .content {padding: 10px;}
	.content .box {
		width: 100%;
	}
}
</style>