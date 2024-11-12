<script setup>
import {ref} from 'vue'

const newTask = ref('');
let theTasks  = ref(JSON.parse(localStorage.getItem('theTasks'))||[]);
const addTask = ()=>{

  if(newTask.value.trim()!==''){

    theTasks.value.push(newTask.value);
    localStorage.setItem('theTasks',JSON.stringify(theTasks.value));

  }
}

const remove = (index)=>{
  theTasks.value.splice(index,1);
  localStorage.setItem('theTasks',JSON.stringify(theTasks.value));
}

</script>




<template>
  <div class="container">
    <h1 class="title">ToDo App</h1>
    <div class="addPart">
      <input v-model="newTask" @keyup.enter="addTask" class="input" type="text" placeholder="Enter a task">
      <button class="btn incrBtn" @click="addTask">Add</button>
    </div>
    <div class="listOfTasks">
      <div v-for="(task,index) in theTasks" :key="index" class="btnInput">
        <p class="theTask">{{ task }}</p>
        <button @click="remove(index)" class="btn decrBtn locBtn">Delete</button>
      </div>
    </div>
  </div>
</template>


<style>

*{
  margin: 0;
}
body{
  display: flex;
  justify-content: center;
  align-items: center;
}

  .container{
    margin-top: 1rem;
    width: 400px;
    border: 1px solid rgb(206, 202, 202);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    border-radius: 10px;
    align-self: center;
    padding-bottom: 1rem;
    padding-top: 1rem;
  }

  .title{
    font-family: Arial, Helvetica, sans-serif;
    font-size: 25px;
    font-weight: bold;
  }

  .addPart{
    display: flex;
    align-items: center;
    justify-content: space-around;
    width: 100%;
    padding: 10px;
    column-gap: 3rem;
  }

  .theTask{
    border: 1px solid rgb(218, 216, 216);
    padding: 3.2px 10px;
    font-family:Verdana, Geneva, Tahoma, sans-serif;
    font-size: 14px;
    border-radius: 3px;
    width: 200px;
    text-wrap: wrap;
    margin-bottom: 0.1rem;
  }

  .listOfTasks{
    width: 100%;
  }

  .btnInput{
    display: flex;
    align-items: center;
    justify-content: space-around;
    width: 100%;
    row-gap: 0.5rem;
  }

  .btn{
    cursor: pointer;
  }

</style>
