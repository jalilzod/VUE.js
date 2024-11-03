<script setup>
  import { reactive } from 'vue'

  let initialState = reactive({count: 0});

  function increment(){
    if(initialState.count==100)
      initialState.count = 100;
    else
      initialState.count++;
  }

  function decrement(){
    if(initialState.count==0)
      initialState.count = 0;
    else
      initialState.count--;
  }

</script>

<template>
    <h1>Count: {{ initialState.count }}</h1>
    <button class="btn incrBtn" v-on:click="increment()">+</button>
    <button class="btn decrBtn" v-on:click="decrement()">-</button>

</template>
