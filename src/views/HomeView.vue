<template>
  <div class="home">
	<HeaderMain/>
	<SobreMim/>
	<TecItem/>
	<ProjItem/>
	<ContatoItem/>
	<FooterItem/>
  </div>
</template>

<script>
import HeaderMain from '../components/header.vue'
import SobreMim from '../components/sobre.vue'
import TecItem from '../components/tecno.vue'
import ProjItem from '@/components/projects.vue'
import ContatoItem from '@/components/contato.vue'
import FooterItem from '@/components/footer.vue'

export default {
	name: 'HomeView',
	components: {
		HeaderMain,
		SobreMim,
		TecItem,
		ProjItem,
		ContatoItem,
		FooterItem
	},
	mounted(){
	}
}
</script>

<style scoped>
.home {
	display: flex;
	justify-content: center;
	flex-wrap: wrap;
}

</style>