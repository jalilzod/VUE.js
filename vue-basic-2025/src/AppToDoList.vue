<script setup>
  import {ref,onMounted} from 'vue';

  const name = ref('Ming Yuan');
  const status = ref(true);
  const tasks = ref(['Task 1','Task 2','Task 3']);
  let changedName = ref('');
  let newTask = ref('');

  const toggleStatus = ()=>{
    status.value = !status.value;
  }

  const changeName = ()=>{
    name.value = changedName.value;
    changedName.value = '';
  }

  const addTask = ()=>{
    if(newTask.value.trim()!==''&&!tasks.value.includes(newTask.value)){
      tasks.value.push(newTask.value);
      newTask.value = '';
    }
  }

  const deleteTask = (index)=>{
    if(tasks.value.length!=0){
      tasks.value.splice(index,1);
    }
  }

  onMounted(async()=>{
    try{
      const response = await fetch('https://jsonplaceholder.typicode.com/todos');
      const data = await response.json();

      tasks.value = data.map((task)=>{
        task.title;
      });
    }catch(error){
      console.log('fetching error');
    } 
  })

</script>

<template>
  <div>
    <h1>{{ name }}</h1>  
    <p v-if="status">User is active</p>
    <p v-else>User is inactive</p>
    <h3>Tasks</h3>
    <ul>
      <li v-for="(task,index) in tasks" :key="task">
        <span>{{ task }}</span>
        <button @click="deleteTask(index)">Delete</button>
      </li>
    </ul>

    <a :href="link">Click for Google</a>
    <button @click="toggleStatus">{{ status?'Inactive':'Active' }}</button>
    <br>
    <input v-model="changedName"  placeholder="Change the name">
    <button @click="changeName">Change name</button>
    

    <form @submit.prevent="addTask">
      <label for="newTask">Add task</label>
      <input type="text" v-model="newTask" placeholder="New task...">
      <button type="submit">Submit</button>
    </form>

  </div>
</template>


