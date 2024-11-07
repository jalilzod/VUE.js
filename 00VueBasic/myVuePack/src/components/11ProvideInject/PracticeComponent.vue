<script setup>
  import {inject} from 'vue'

let admins = inject('admin');
let games = inject('games');

</script>


<template>
  <h1>Admins</h1>
  <ul v-for="(admin,index) in admins" :key="index">
      <li>{{ admin }}</li>
  </ul>
  <h1>Games</h1>
  <ul>
      <li>{{ games.id }}</li>
      <li>{{ games.title }}</li>
      <li>{{ games.genre }}</li>
      <li>{{ games.platform }}</li>
      <li>{{ games.developer }}</li>
  </ul>

</template>
