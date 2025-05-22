<script setup>
import {ref} from 'vue'

const userName = ref('');
const userPassword = ref('');
const userRole = ref('User');
const users = ref([
]);


const handleForm = ()=>{
  
  users.value.push({
    username: userName.value,
    password: userPassword.value,
    role: userRole.value
  })


  userName.value = '';
  userPassword.value = '';
  userRole.value = '';
  
  
};


const deleteUser = (index)=>{
  users.value.splice(index,1);
}

</script>




<template>


<div>
<form class="form-user" @submit.prevent="handleForm">
  <input v-model="userName" type="text" placeholder="Username">
  <input v-model="userPassword" type="password" placeholder="Password">
  <label >Role</label>
  <select v-model="userRole">
    <option value="user">User</option>
    <option value="admin">Admin</option>
  </select>
  <button type="submit">Submit</button>

</form>

<div>
  <ul>
    <li v-for="(us,index) in users" :key="index">
      <span>{{ us.username }}</span>
      <span>{{ us.password }}</span>
      <span>{{ us.role }}</span>
      <button @click="deleteUser(index)">Delete</button>
    </li>
  </ul>
</div>
</div>


</template>

<style scoped>
.form-user{
  display: flex;
  flex-direction: column;
  max-width: 400px;
  height: 200px;
  justify-content: center;
  align-items: center;
  background-color: rgb(2, 50, 156);
  border-radius: 10px;
  gap: 5px;
  margin-bottom: 50px;
}

ul{
  background: gray;
  padding: 20px;
  border-radius: 10px;
  width: 600px;
  list-style: none;
}

li{
  display: flex;
  justify-content: start;
  align-items: center;

}

li span{
  width: 130px;
}

button{
  background: red;
  border: none;
  color: white;
  border-radius: 3px;
  padding: 2px 5px;
}


</style>