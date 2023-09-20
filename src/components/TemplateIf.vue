<script setup>
    import { ref } from 'vue';

    const ok = 'A';

    const s = ref(true);
</script>


<template v-if="ok === 'A'">
    <h1>Title</h1>
    <p>Paragraph 1</p>
    <p>Paragraph 2</p>
    <button @dblclick="s = !s">Toggle Show : Double Click</button>
    <p v-show="s">Paragraph 3</p>
</template>
