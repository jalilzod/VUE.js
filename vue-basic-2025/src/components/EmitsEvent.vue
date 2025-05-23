<script setup>

import {ref} from 'vue';

const name = ref('');
const email = ref('');
const password = ref('');
const emit = defineEmits(['formHandler']);

const submitForm  = ()=>{
    emit('formHandler',name.value,email.value,password.value);
}

</script>

<template>
    <div>
        <button @click="$emit('increment')">➕</button>
        <button @click="$emit('decrement')">➖</button>

        <form class="student" @submit.prevent="submitForm">
            <input type="text" placeholder="Enter name" v-model="name">
            <input type="email" placeholder="Enter email" v-model="email">
            <input type="password" placeholder="Enter password" v-model="password"> 
            <button class="simpleBtn" type="submit">Submit</button>

        </form>

    </div>
</template>