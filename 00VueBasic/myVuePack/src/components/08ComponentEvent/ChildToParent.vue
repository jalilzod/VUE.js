

<script setup>

import {ref} from 'vue'

let userName = ref('');
let userEmail = ref('');
let userPassword = ref('');


</script>


<template>

  <form @submit.prevent="$emit('userForm',userName,userEmail,userPassword)" class="form">
      <input class="input" type="text" placeholder="Enter your name" v-model="userName">
      <input class="input" type="email" placeholder="Enter your email" v-model="userEmail">
      <input class="input" type="password" placeholder="Enter your password" v-model="userPassword">
      <button type="submit" class="btn incrBtn">Submit</button>
  </form>

</template>


<style>
</style>
