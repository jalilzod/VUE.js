<script setup>

  import {ref} from 'vue'
  import CompOne from './CompOne.vue'
  import ComponentTwo from './ComponentTwo.vue'
  import ComponentThree from './ComponentThree.vue'

  const currentComp = ref('CompOne');
  const tabs= {
    CompOne,
    ComponentTwo,
    ComponentThree
  }

</script>




<template>

  <button class="btn incrBtn" @click="currentComp='CompOne'">Comp1</button>
  <button class="btn incrBtn" @click="currentComp='ComponentTwo'">Comp2</button>
  <button class="btn incrBtn" @click="currentComp='ComponentThree'">Comp3</button>

<component :is="tabs[currentComp]"/>


</template>
