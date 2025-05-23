<script setup>
import { ref } from 'vue'
import UserForm from './components/UserForm.vue'
import UserList from './components/UserList.vue'


</script>

<template>
  <div>
    <h1>Vue Component Communication</h1>
    <UserForm @add-user="addUser" />
    <UserList :users="users" />
  </div>
</template>
