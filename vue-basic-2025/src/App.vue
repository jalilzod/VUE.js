<script setup>
  import {ref,watch} from 'vue';


  const tasks = ref([
    {
      id:1,
      title:'task 1',
      done: false
    },
    {
      id:2,
      title:'task 1',
      done: false
    },
    {
      id:3,
      title:'task 1',
      done: false
    },
    {
      id:4,
      title:'task 1',
      done: false
    },

  ]);

  
  const doneTask = (index)=>{
    tasks.value.at(index).done = !tasks.value.at(index).done;
    console.log('clicked...'+tasks.value.at(index).done);
  }


</script>



<template>
  <ul class="task-table">
    <li class="list" v-for="(task,index) in tasks" :key="index">
        <span>{{ task.title }}</span>
        <button @click="doneTask(index)" :class="{doneStyle: task.done}" >{{ task.done?'Undone':'Done' }}</button>
    </li>
  </ul>
</template>



<style scoped>

  .task-table{
    list-style: none;
    display: flex;
    flex-direction: column;
    max-width: 400px;
    gap: 10px;
  }

  .list{
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .list button{
    background: rgb(5, 84, 180);
    border: none;
    color: white;
    border-radius: 3px;
    padding: 5px 10px;
    transition: 0.2s;
  }

  .list button:hover{
    background: rgb(5, 75, 161);
    color: gray;
  }

  .doneStyle{
    background: rgb(60, 61, 62)!important;
    color: white!important;
  }

</style>