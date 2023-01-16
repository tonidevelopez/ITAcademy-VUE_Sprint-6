<template>
    <ul>
        <li v-for="frase in frases" :key="frase.id">{{ frase.txt }}</li>
    </ul>
</template>

<script setup>
defineProps(['frases'])
</script>