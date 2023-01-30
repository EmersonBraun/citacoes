<template>
	<div id="app">
		<keep-alive>
			<component :is="component"></component>
		</keep-alive>
		<span>
			<button @click="toogle">{{ component }}</button>
		</span>
		<Footer />
	</div>
</template>

<script>
import Quotes from './components/Quotes.vue'
import About from './components/About.vue'
import Footer from './components/Footer.vue'

export default {
	components: { Quotes, About, Footer },
	methods: {
		toogle() {
			this.component = this.component === 'Quotes' ? 'About' : 'Quotes'
		}
	},
	data() {
		return {
			component: 'Quotes'
		}
	},
}
</script>

<style>
	#app {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100vh;
		font-size: 1.6rem;
	}

	button {
        outline: none;
        padding: 5px 15px 10px;
        margin: 10px 5px;
        border-radius: 3px;
        font-size: 2rem;
        font-weight: 300;
        color: #FFF;
        background-color: rgba(0, 0, 0, .5);
    }
</style>