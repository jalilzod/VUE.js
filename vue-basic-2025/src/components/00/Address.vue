<script setup>

import { inject } from 'vue';

const name = inject('studentName');
const age = inject('studentAge');
const location = inject('location');

</script>

<template>
    <div class="student">
        <h1>{{ name }}</h1>
        <h1>{{ age }}</h1>
        <h1>{{ location.country }}</h1>
        <h1>{{ location.city }}</h1>
        <h1>{{ location.street }}</h1>
    </div>
</template>
