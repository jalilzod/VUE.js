<script setup>
import {ref} from 'vue';
const number = ref(0);
</script>

<template>
    
    <div>
        <h2>Number: {{ number }}</h2>
        <button class="simpleBtn" @click="number++">Increment</button>
    </div>

</template>