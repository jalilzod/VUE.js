<script setup>

import {ref,computed} from 'vue';

const adminName = ref('Ming');
const adminAge = ref(1998);
const currentYear = new Date().getFullYear();

const detail = computed(()=>{
  return `${adminName.value} ${currentYear-adminAge.value}`
})

const number = ref(5);
const sqr = computed(()=>{
  return number.value*number.value;
})


</script>


<template>

  <h1>Detail: {{detail}}</h1>
  <h2>Number: {{ number }}</h2>
  <h2>Squared: {{ sqr }}</h2>

  <button class="btn incrBtn" @click="number++">Increment</button>
  <button class="btn decrBtn" @click="number=0">Reset</button>


</template>


<style>
</style>
