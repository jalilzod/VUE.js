<script setup>
import PracticeComponent from './components/11ProvideInject/PracticeComponent.vue'
import o2UserForm from './components/01Events/o2UserForm.vue'
import o1Event from './components/01Events/o1Event.vue'
import {provide} from 'vue'

provide(
  'admin',
  ['ming','yuan','yang'],
)

provide(
  'games',{
    id:1,
    title:'Mafia',
    genre: ['action','advanture','rpg'],
    platform: ['pc','xBox','PlayStation'],
    developer: {
      name: 'mingyuan',
      location: 'Shanghai',
      teamSize: 50
    }
  })



</script>

<template>
   <PracticeComponent />
</template>

<style scoped></style>
