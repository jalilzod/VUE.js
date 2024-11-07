

<script setup>
  // const props = defineProps(['name','last']);
 //we cannot change the value of propss
  //console.log(props);

  defineProps({
    users: Array,
    userInfo: Object
  })

</script>


<template>

  <ul v-for="(user,index) in users" :key="index">
      <li>{{ user }}</li>
  </ul>
  <hr>
  <ul v-for="(userIn,index) in userInfo" :key="index">
      <li>{{ userIn }}</li>
  </ul>

</template>


<style>
</style>
