<script setup>
import { reactive  } from 'vue';

const student = reactive({
    name: 'Mingyuan',
    age: 27,
    isStudent:false
});

</script>


<template>

    <div class="student">
        <span>Name: {{ student.name }}</span>
        <span>Age: {{ student.age }}</span>
        <span>Status: {{ student.isStudent?'Student':'Employee' }}</span>
    </div>

</template>


