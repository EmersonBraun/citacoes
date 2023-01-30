<template>
    <div class="quotes">
        <span>
            <button @click="prev">&lt;</button>
            <button @click="random">Random</button>
            <button @click="next">&gt;</button>
        </span>
        <Quote>
            <template v-slot:author>
                <h1>{{ quotes[index].author }}</h1>
            </template>
            <template v-slot:quote>
                <p>{{ quotes[index].quote }}</p>
            </template>
            <template v-slot:profession>
                <h6>{{ quotes[index].profession }}</h6>
            </template>
            <template v-slot:topics>
                <h6>{{ quotes[index].topics.join(', ') }}</h6>
            </template>
        </Quote>
    </div>
</template>

<script>
import Quote from './Quote.vue'
import { quotes } from "../quotes";
export default {
    components: { Quote },
    methods: {
        next() {
            this.number++
        },
        prev() {
            this.number--
        },
        random() {
            this.number = Math.floor(Math.random() * this.quotes.length)
        }
    },
    data() {
        return {
            number: 0,
            quotes
        }
    },
    computed: {
        index() {
            return this.number % this.quotes.length
        }
    }
}
</script>

<style scoped>
.quotes {
    display: flex;
    flex-direction: column;
    align-items: center;
}
</style>
