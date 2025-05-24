<script setup>
import {ref} from 'vue';
import ComponentOne from './components/ComponentOne.vue';
import ComponentTwo from './components/ComponentTwo.vue';
import ComponentThree from './components/ComponentThree.vue';

const current = ref('ComponentOne');

const tabs = {
  ComponentOne,
  ComponentTwo,
  ComponentThree
}


</script>

<template>
  <div class="student">
    <button @click="current = 'ComponentOne'">Cp 1</button>
    <button @click="current = 'ComponentTwo'">Cp 2</button>
    <button @click="current = 'ComponentThree'">Cp 3</button>
    <component :is="tabs[current]"/>
  </div>
</template>
