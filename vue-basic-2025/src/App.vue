<script setup>
import {ref} from 'vue';
import EmitsEvent from './components/EmitsEvent.vue';

const number = ref(0);
const userName =  ref('');
const userEmail =  ref('');
const userPassword =  ref('');


const handleForm = (name,email,password)=>{
    userName.value = name;
    userEmail.value = email;
    userPassword.value = password;
}


</script>

<template>
  <div class="student">
    <span>Number: {{ number }}</span>
    <EmitsEvent  @formHandler="handleForm"/>

    <span>{{ userName }}</span>
    <span>{{ userEmail }}</span>
    <span>{{ userPassword }}</span>

  </div>
</template>
