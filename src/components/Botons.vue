<template>
    <div>
        <button @click="$emit('previousSentence')">Anterior</button>
        <button @click="$emit('nextSentence')">Següent</button>
    </div>
</template>

<script>
export default {
    name: 'Botons',
}
</script>

<style scoped>
button {
    width: 50%;
    padding: 1rem;
    font-size: 1.2rem;
}
</style>