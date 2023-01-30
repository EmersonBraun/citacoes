<template>
	<div id="app">
		<span>
			<button @click="componente = 'Quotes'">Quotes</button>
			<button @click="componente = 'About'">About</button>
		</span>
		<keep-alive>
			<component :is="componente"></component>
		</keep-alive>
	</div>
</template>

<script>
import Quotes from './components/Quotes.vue'
import About from './components/About.vue'

export default {
	components: { Quotes, About },
	data() {
		return {
			componente: 'Quotes'
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