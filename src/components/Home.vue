<template>
    <div v-if="!mostrarEscena" class="benvingut">
        <h2>Benvingut a aquest tutorial, on trobaràs uns petits consells del nostre heroi</h2>
        <button @click="start">Començar</button>
    </div>
    <div v-else class="image" :style="{ backgroundImage: `url(src/assets/${currentImage}.jpg)` }">
        <Botons @previousSentence="previousSentence" @nextSentence="nextSentence" />
        <Escena :frases='frases' :currentSentence="currentSentence" />
    </div>
</template>

<script>
import Escena from './Escena.vue'
import Botons from './Botons.vue'
import { frases } from '../assets/frases.js'

export default {
    name: 'Home',
    components: { Escena, Botons },
    data() {
        return {
            frases: frases,
            currentSentence: 1,
            currentImage: 1,
            mostrarEscena: false
        }
    },
    methods: {
        previousSentence() {
            if (this.currentSentence !== 1) {
                this.currentSentence--
                this.currentImage--
            }
        },
        nextSentence() {
            if (this.currentSentence !== 4) {
                this.currentSentence++
                this.currentImage++
            }
        },
        start() {
            this.mostrarEscena = !this.mostrarEscena
        }
    }
}
</script>

<style scoped>
.benvingut {
    min-height: 40vh;
    background-color: rgb(222, 99, 65);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    border-radius: 150px;
    padding: 50px;
}

.benvingut h2 {
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    color: white;
    font-weight: bold;
    margin-top: 20px;
}

.benvingut button {
    margin-top: 40px;
    width: 150px;
    height: 40px;
    font-size: 1rem;
    border-radius: 20px;
}

.image {
    height: 100vh;
    background-size: 100%;
    background-repeat: no-repeat;
    background-position: 0% 0%;
}
</style>