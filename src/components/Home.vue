<template>
    <div>
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
            currentSentence: 1
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
        }
    }
}
</script>