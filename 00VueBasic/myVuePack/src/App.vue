<script setup>
import PropsVue from './components/07Props/PropsVue.vue'
import o2UserForm from './components/01Events/o2UserForm.vue'
import o1Event from './components/01Events/o1Event.vue'
import{ref} from 'vue'
const firstName = ref('Ming');
const lastName = ref('Yuan');


</script>

<template>
  <PropsVue :name="firstName" :last="lastName"/>
</template>

<style scoped></style>
