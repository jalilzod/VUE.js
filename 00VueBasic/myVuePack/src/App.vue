<script setup>
import ChildToParent from './components/08ComponentEvent/ChildToParent.vue'
import o2UserForm from './components/01Events/o2UserForm.vue'
import o1Event from './components/01Events/o1Event.vue'
import{ref} from 'vue'
// const firstName = ref('Ming');
// const lastName = ref('Yuan');

const count = ref(0);

const handleUserForm = (userName,userEmail,userPassword)=>{

  console.log("User: ",userName);
  console.log("Email: ",userEmail);
  console.log("Password: ",userPassword);

}

</script>

<template>
  <h1>Count: {{ count }}</h1>
   <ChildToParent @userForm="handleUserForm"/>
</template>

<style scoped></style>
