<script setup>
const adminName = 'MingYuan'
const adminAge = 25

function adminDetails() {
  return `admin name: ${adminName}, admin age: ${adminAge}`
}
</script>

<template>
  <h1>Hello,admin: {{ adminName }}</h1>
  <h1>Adming age: {{ adminAge }}</h1>
  <h1>Admin details: {{ adminDetails() }}</h1>
</template>

<style>
h1 {
  color: rgb(6, 6, 80);
}
</style>
