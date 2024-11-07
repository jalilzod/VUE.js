<script setup>
import {inject} from 'vue'


const userName = inject('userName');
const userEmail = inject('userEmail');
const userAge = inject('userAge');


</script>


<template>

  <h1>User component</h1>
  <h1>{{ userName }}</h1>
  <h1>{{ userEmail }}</h1>
  <h1>{{ userAge }}</h1>

</template>
