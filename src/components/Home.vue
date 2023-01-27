<template>
    <div v-if="!mostrarEscena" class="benvingut">
        <h2>Benvingut a aquest tutorial, on trobaràs uns petits consells del nostre heroi</h2>
        <button @click="start">Començar</button>
    </div>
    <div v-else>
        <Botons @previousSentence="previousSentence" @nextSentence="nextSentence" />
        <Escena :frases='frases' :currentSentence="currentSentence" />
    </div>
</template>

<script>
import Escena from './Escena.vue'
import Botons from './Botons.vue'

export default {
    name: 'Home',
    components: { Escena, Botons },
    data() {
        return {
            frases: [
                {
                    txt: "El nostre heroi estava surant per l'espai sideral quan a la llunyania va albirar una nau espacial",
                    id: 1
                },
                {
                    txt: "Sentia curiositat per l'interior de la nau i es va posar a inspeccionar-la. Va arribar a una sala amb dues portes.",
                    id: 2
                },
                {
                    txt: "L'heroi va decidir travessar la porta que el portava a casa",
                    id: 3
                },
                {
                    txt: "Mentrestant, altres herois no van tenir tanta sort en la seva elecció ...",
                    id: 4
                },
            ],
            currentSentence: 1,
            mostrarEscena: false
        }
    },
    methods: {
        previousSentence() {
            if (this.currentSentence !== 1) {
                this.currentSentence--
            }
        },
        nextSentence() {
            if (this.currentSentence !== 4) {
                this.currentSentence++
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
</style>