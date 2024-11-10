<script setup>
import {ref} from 'vue'


let message   =  ref('You should learn  js and vue');



</script>


<template>
  <h1>{{ message }}</h1>
  <button>Change text</button>
</template>
