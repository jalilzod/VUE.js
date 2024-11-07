<script setup>
import {ref} from 'vue'

const formatData = ref({
  userName:'',
  email:'',
  password:''
});

function handleRegister(){
  alert('Successfull...');
}

</script>


<template>
  <form class="form" @submit.prevent="handleRegister">
    <input class="input" type="text" placeholder="Enter your name" v-model="formatData.userName">
    <input class="input" type="email" placeholder="Enter your email" v-model="formatData.email">
    <input class="input" type="password" placeholder="Enter your password" v-model="formatData.password">
    <button class="btn incrBtn" type="submit">Submit</button>
  </form>
    <h1>{{ formatData.userName }}</h1>
    <h1>{{ formatData.email }}</h1>
    <h1>{{ formatData.password }}</h1>

</template>


<style>
h1{
  margin: 0;
  text-align: center;
  font-size: 24px;
  color: rgb(3, 3, 86);
}
</style>
