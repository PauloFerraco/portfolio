<template>
	<section class="tecn" data-scroll-reveal="enter top move 50px, after 0.9s">
		<div class="title">Tecnologias</div>
		<div class="content">
			<div class="box box-ani" v-for="(t, i) in tecs" :key="i">
				<ToolTip :title="t.title" />
				<div class="tec" v-html="t.icon"></div>
			</div>
		</div>
	</section>
</template>

<script>
import ToolTip from '@/components/utils/tooltip'
// import { gsap } from 'gsap';
import ScrollReveal from 'scrollreveal'

export default {
	name: 'TecItem',
	components: {
		ToolTip,
	},
	data() {
		return {
			tecs: [
				{
					'title': 'HTML',
					'icon': '<i class="fa-brands fa-html5"></i>'
				},
				{
					'title': 'JavaScript',
					'icon': '<i class="fa-brands fa-js"></i>'
				},
				{
					'title': 'VueJS',
					'icon': '<i class="fa-brands fa-vuejs"></i>'
				},
				{
					'title': 'PHP',
					'icon': '<i class="fa-brands fa-php"></i>'
				},
			]
		}
	},
	methods: {
	},
	mounted(){
		ScrollReveal().reveal('.content .box-ani', {
			reset:true,
			origin: 'top',
			distance: '60px',
			delay: 300,
			easing: 'ease-in',
			scale: 0.5
		})
	}
}
</script>

<style scoped>

.tecn .content {
	width: 600px;
	height: 300px;
	display: flex;
	justify-content: space-evenly;
	align-items: center;
	flex-wrap: wrap;
}

.tecn .content .box {
	position: relative;
	width: 100px;
	height: 100px;
	border: 1px solid rgba(255,255,255,.15);
	border-radius: 6px;
	text-align: center;
	line-height: 100px;
	font-size: 40px;
	color: var(--font);
	transition: all .3s ease-in-out;
	margin: 4px;
}
.tecn .content .box:hover {
	color: var(--blue);
	border-color: var(--blue);
}
</style>