<script setup>
    import { ref } from 'vue';

    const parentMessage = ref('Parent')
    const items = ref([{ message: 'Foo' }, { message: 'Bar' }]) 
</script>


<template>

    <li v-for="(item, index) in items">
    {{ parentMessage }} - {{ index }} - {{ item.message }}
    </li>

</template>