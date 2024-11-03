<script setup>
  import { ref } from 'vue'

  let users = ref(['Ming','Yuan','Yang','Jaha','Bexa']);
  let index = ref(0);

  function nextUser(){
    index.value = (index.value+1)%users.value.length;

  }
  function prevUser(){
    index.value =  (index.value-1+users.value.length)%users.value.length;

  }


</script>

<template>
    <h1>Users: {{ users[index] }}</h1>
    <button class="btn incrBtn" @click="nextUser()">Next User</button>
    <button class="btn decrBtn" @click="prevUser()">Prev User</button>

</template>
