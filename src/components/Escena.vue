<template>
    <ul>
        <li v-for="frase in frases" :key="frase.id">{{ frase.txt }}</li>
    </ul>
</template>

<script setup>
defineProps(['frases'])
</script>

<style scoped>
li {
    list-style: none;
    text-align: center;
    border: 1px solid black;
    border-radius: 20px;
    padding: .5rem;
    margin-bottom: 1rem;
}
</style>