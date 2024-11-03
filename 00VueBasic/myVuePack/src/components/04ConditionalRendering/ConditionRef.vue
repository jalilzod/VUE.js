
<script setup>
import { ref } from 'vue'

const age = ref(26);
const isStudent = ref(false);
const show = ref(true);

</script>


<template>
  <h1 v-if="isStudent&&age>=18&&age<25">Dont rush!!</h1>
  <h1 v-else-if="isStudent&&age>=25">Hurry up!!</h1>
  <h1 v-else>You are not allowed!!!</h1>

  <div v-if="show">
    <h1>Welcome</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Minus quas non repellat, delectus quasi temporibus iure harum impedit illum ea.</p>

  </div>
  <button class="btn incrBtn" @click="show = !show">More</button>
</template>
