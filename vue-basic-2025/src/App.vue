<script setup>
import {ref,provide} from 'vue';
import ProvideInject from  './components/ProvideInject.vue'



provide('studentName','Mingyuan');
provide('studentAge',27);
provide('location',{country: 'tajikistan',city: 'Dushanbe',street: 'Jomi'});

</script>

<template>
  <div class="student">
    <ProvideInject />
  </div>
</template>
