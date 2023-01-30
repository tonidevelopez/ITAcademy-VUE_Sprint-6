<template>
    <div>
        <ul>
            <li v-for="frase in frases" :key="frase.id" :class="{ resaltada: frase.id === currentSentence }">{{
                frase.txt
            }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Escena',
    props: ['frases', 'currentSentence']
}
</script>

<style scoped>
ul {
    padding: 0;
    list-style: none;
    margin: 1rem;
}

li {
    text-align: center;
    border: 1px solid black;
    border-radius: 20px;
    padding: .5rem;
    margin-bottom: 1rem;
    background-color: rgba(255, 255, 255, .8);
}

.resaltada {
    background-color: rgb(222, 99, 65);
    color: white;
}
</style>