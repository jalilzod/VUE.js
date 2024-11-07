

<script setup>
  const props = defineProps(['name','last']);
 //we cannot change the value of propss
  console.log(props);
</script>


<template>
  <h1>{{ props.name  }}</h1>
  <h1>{{ props.last  }}</h1>

</template>


<style>
</style>
