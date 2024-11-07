<script setup>

import {ref} from 'vue'

let txt = ref('Sign In');

let Ru = ()=>{
  txt.value = 'Войти'
}

let En = ()=>{
  txt.value = 'Log In'
}

</script>



<template>
  <h1>Hello</h1>
  <button class="btn hl">{{ txt }}</button>
  <button v-on:click="Ru" class="btn incrBtn">Ru</button>
  <button v-on:click="En" class="btn incrBtn">En</button>
</template>

<style>

.hl{
  background-color: darkred;
}

</style>
