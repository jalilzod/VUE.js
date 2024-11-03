<script setup>
import { ref } from 'vue'
let count = ref(0)

function increment() {
  count.value++
}

function decrement() {
  count.value--
}
</script>

<template>
  <h1>Count: {{ count }}</h1>
  <button class="incrBtn btn" v-on:click="increment()">Increase</button>
  <button class="decrBtn btn" v-on:click="decrement()">Decrease</button>
</template>

<style>
.btn {
  border: none;
  padding: 4px 20px;
  margin-right: 0.5rem;
  border-radius: 3px;
  color: white;
  font-weight: bold;
  transition: 0.1s;
}
.incrBtn {
  background-color: rgb(72, 72, 255);
}

.decrBtn {
  background-color: darkred;
}

.btn:active {
  background-color: darkgray;
}
</style>
