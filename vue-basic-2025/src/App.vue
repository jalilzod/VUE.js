<script setup>

import {ref,computed, compile} from 'vue';

const tasks = ref([]);
const completedTasks = ref([]);

const currentTask = ref('');
const currentDate = ref('');


const formattedDate = computed(()=>{
  if(!currentDate.value) return ''
  const date = new Date(currentDate.value);
  const year = date.getFullYear();
  const month  = String(date.getMonth()+1).padStart(2,'0');
  const day = String(date.getDay()).padStart(2,'0');

  return `${year}-${month}-${day}`;

})

const addTask = ()=>{
  if(currentDate.value&&currentTask.value){
      tasks.value.push({
        title: currentTask.value,
        date: currentDate.value
      })
  }

  currentTask.value = '';
  currentDate.value = '';
}


const deleteTask = (index)=>{
  tasks.value.splice(index,1);
}

const editTask = (index)=>{
  const tmp = tasks.value.at(index);
}

const completeTask = (index)=>{
  const tmp = tasks.value.at(index);
  completedTasks.value.push(tmp);

  
}

</script>


<template>

  <div class="parentController">
    <form class="theTask" @submit.prevent="addTask">
      <input v-model="currentTask" type="text" placeholder="Enter a new task.... ">
      <input v-model="currentDate" type="date" placeholder="Pick a date..">
      <button type="submit">Add➕</button>
    </form>

    <ul class="showTasks">
      <li class="allPart" v-for="(task,index) in tasks" :key="index">
        <div style="flex: 2" >
          <span>{{ task.title }}</span>
        </div>
        <div style="flex: 0.5" >
          <span>{{ task.date }}</span>
        </div>
        <div style="flex: 1" >
          <button class="del btn" @click="deleteTask(index)">Delete</button>
          <button class="edit btn" @click="editTask(index)">Edit</button>
          <button class="complt btn" @click="completeTask(index)">Completed</button>
        </div>
      </li>
    </ul>
  </div>

</template>

<style>

  .theTask{
    display: flex;
    max-width: 400px;
    justify-content: space-around;
    align-items: center;
    background-color: rgb(6, 84, 173);
    padding: 20px;
    border-radius: 10px;
    box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
  }

   .theTask input{
    outline: none;
    padding: 5px 10px;
    border-radius: 3px;
    border: 0;
   }

   .theTask button{
    background-color: rgb(79, 202, 3);
    border: 0;
    color: rgb(63, 62, 62);
    padding: 4px 10px;
    border-radius: 5px;
   }

     .theTask button:hover{
      color: gray;
     }

     .showTasks{
      max-width: 600px;
      border-radius: 5px;
      color: white;
      display: flex;
      list-style: none;
      gap: 10px;
      background-color: gray;
      display: flex;
      flex-direction: column;
      border: 1px solid black;
      padding-top: 5px;
      padding-bottom: 5px;

     }

     .allPart{
      display: flex;
      justify-content: space-around;

     }

     .btn{
      border: 0;
      padding: 2px 5px;
      margin-right: 2px;
      border-radius: 3px;
     }

     .btn:hover{
      color: gray;
     }

     .del{
      background-color: rgb(196, 7, 7);
      color: white;
     }

     .edit{
      background-color: rgb(30, 93, 241);
      color: white;
     }

     .complt{
      background-color: rgb(15, 173, 6);
      color: rgb(3, 3, 3);
     }


</style>