<script setup>
import StaticProps from './components/StaticProps.vue';
import {ref} from 'vue';

const firstN = ref('Mingyuan');
const lastN = ref('Yuan');
let tmpN = ref('');
let tmpF = ref('');


const changeName = ()=>{
  firstN.value = tmpN.value; 
  lastN.value = tmpF.value; 

  console.log(tmpN.value+tmpF.value);
}

</script>

<template>
  <div>
    <input type="text" placeholder="Enter f name" v-model="tmpN">
    <input type="text" placeholder="Enter l name" v-model="tmpF">
    <button @click="changeName">Change name</button>
   <StaticProps :firstName="firstN" :lastName="lastN"/>
  </div>
</template>
