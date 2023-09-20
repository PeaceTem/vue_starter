<script setup>
    import { ref } from 'vue'

    const awesome = ref(false);

    const type = 'B';
</script>

<template>
    <button @click="awesome = !awesome">Toggle</button>

    <h1 v-if="awesome" >Vue is awesome!</h1>
    <h1 v-else>Oh no 😢</h1>

    <div v-if="type === 'A'">
        A
    </div>
    <div v-else-if="type === 'B'">
        B
    </div>
    <div v-else-if="type === 'C'">
        C
    </div>
    <div v-else>
        Not A/B/C
    </div>
</template>