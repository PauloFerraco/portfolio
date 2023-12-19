<template>
	<section class="proj">
		<div class="title">Projetos</div>
		<div class="content">
			<swiper :slidesPerView="4" :spaceBetween="10" :centeredSlides="false" :pagination="{clickable: true,}" class="mySwiper">
				<SwiperSlide class="box box-pro" v-for="(p, i) in projs" :key="i" :style="{backgroundImage: 'url('+p.image+')'}">
					<span class="name">{{ p.title }}</span>
					<div class="data" v-html="p.text"></div>
					<div class="date">{{ p.date }}</div>
					<a :href="p.link" target="_blank" rel="noopener noreferrer">
						<button :style="{opacity: p.link != '' ? '1' : '0'}">Ver</button>
					</a>
				</SwiperSlide>
			</swiper>
		</div>
	</section>
</template>

<script>
import ScrollReveal from 'scrollreveal';
import { Swiper, SwiperSlide } from 'swiper/vue';

import 'swiper/css';
// import 'swiper/css/pagination';
// import './style.css';

export default {
	name: 'ProjItem',
	components: {
		Swiper,
		SwiperSlide,
	},
	data() {
		return {
			limit: 4,
			projs: [
				{
					"title": "PowerPanel",
					"text": "Painel de gerenciamento web, feito em VueJS e PHP. Para mais informações entrar em contato na parte 'Contatos'.",
					"link": "",
					"image": "https://ppanel.pauloferraco.com.br/imagem/uploads/upload-fe03e1037bb767dc6c4fbbb898e9ad29.png",
					"date": 2023
				},
				{
					"title": "Bubblet",
					"text": "Site feito ultilizando VueJS e PHP para fã-site de jogo online.",
					"link": "https://bubblet.com.br/",
					"image": "https://ppanel.pauloferraco.com.br/imagem/uploads/upload-6d8a71aa31e62edc3d2e46077226fcc7.png",
					"date": 2023
				},
				{
					"title": "Rádiohabblet",
					"text": "Site feito ultilizando VueJS e PHP para fã-site de jogo online.",
					"link": "https://radiohabblet.com.br/",
					"image": "https://ppanel.pauloferraco.com.br/imagem/uploads/upload-a4f8aecbb95d78efbbbdc3ba9f987893.png",
					"date": 2022
				},
			]
		}
	},
	mounted() {
		ScrollReveal().reveal('.content .box-pro', {
			reset:true,
			origin: 'top',
			distance: '60px',
			delay: 200,
			easing: 'ease-in',
			scale: 0.5
		})
		if(navigator.userAgentData.mobile){
			this.limit = 1
		}
	}
}
</script>

<style scoped>

.swiper {overflow-y: unset;}

.proj .content {
	width: 100%;
	height: auto;
}

.proj .content .box {
	position: relative;
	width: calc(25% - 6px) ;
	height: 200px;
	margin-top: 6px;
	background-color: rgba(0,0,0,.3);
	background-size: cover;
	background-position: center;
	border-radius: 4px;
	border: 1px solid var(--blue);
}

.proj .content .box .data {
	position: relative;
	width: calc(100% - 10px);
	height: calc(100% - 10px);
	background-color: rgba(0,0,0,.6);
	margin: 5px;
	border-radius: 4px;
	color: var(--font);
	text-align: justify;
	padding: 20px;
	font-size: 14px;
	line-height: 20px;
	visibility: hidden;
	opacity: 0;
	transition: all .3s ease;
}
.proj .content .box:hover .data {visibility: visible;opacity: 1;}

.content .box button {
	position: absolute;
	right: 10px;
	bottom: 10px;
	width: auto;
	height: 30px;
	padding: 0 30px;
	border: 1px solid var(--blue);
	background-color: rgba(0,0,0,.4);
	border-radius: 4px;
	font-size: 14px;
	font-weight: 600;
	cursor: pointer;
	transition: all .6s ease-in-out;
}
.content .box:hover button {
	box-shadow: 40px 0 30px -10px rgba(25, 83, 235, 1) inset;
	color: #fff;
}

.content .box .date {
	position: absolute;
	bottom: 14px;
	left: 14px;
	width: auto;
	height: 26px;
	background-color: var(--blue);
	color: var(--font);
	font-weight: 600;
	font-size: 13px;
	padding: 0 10px;
	border-radius: 8px;
	line-height: 26px;
	opacity: 0;
	transition: all .3s ease-in;
}
.content .box:hover .date {opacity: 1;}

.box .name {
	position: absolute;
	width: 100%;
	height: 20px;
	font-size: 15px;
	line-height: 20px;
	top: 8px;
	left: 8px;
	transition: all .4s ease-in-out;
}
.box:hover .name {top: -26px;}
.box .name::before {
	position: absolute;
	content: '';
	top: 0;
	left: -8px;
	width: 2px;
	height: 20px;
	background-color: var(--blue);
	opacity: 0;
	transition: all -3s linear;
}
.box:hover .name::before {
	opacity: 1;
}


@media only screen and (max-width: 500px) {
	.proj .content {padding: 0 10px;}
	.proj .content .box {
		width: calc(100% - 20px) !important;
	}
}
</style>