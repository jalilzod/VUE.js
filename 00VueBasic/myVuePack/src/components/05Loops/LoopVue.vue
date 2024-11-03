
<script setup>
import { ref } from 'vue'

const age = ref(26);
const isStudent = ref(false);
const show = ref(true);

</script>


<template>
  <h1 v-if="isStudent&&age>=18&&age<25">Dont rush!!</h1>
  <button class="btn incrBtn" @click="show = !show">More</button>
</template>
