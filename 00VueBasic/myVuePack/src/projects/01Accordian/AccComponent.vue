<script setup>

import {ref} from 'vue'

const items = ref([
  {
    title: 'What is fron-end?',
    content: 'Front-end development is the process of building components that interact with users. Examples are the user interface, buttons, user-entered data, websites, and user experience (UX) features.',
    open: false
  },

  {
    title: 'What is back-end?',
    content: `Back-end development means working on server-side software, which focuses on everything you can't see on a website. Back-end developers ensure the website performs correctly, focusing on databases, back-end logic, application programming interface (APIs), architecture, and servers.`,
    open: false
  },
  {
    title: 'What is full-stack?',
    content: `Full stack development is the process of developing both the frontend and backend of applications. Any application has a frontend (user-facing) component and a backend (database and logic) component. The frontend contains the user interface and code related to user interactions with the application.`,
    open: false
  },



])

const toggleAccor = (index)=>{
  items.value  = items.value.map((item,i)=>({
    ...item,
    open: i==index ? !item.open : false
  }))
}

</script>



<template>
  <div class="container">
    <div v-for="(item,index) in items" :key="index" class="acc">
      <div class="header" @click="toggleAccor(index)">
          {{ item.title }}
          <span>{{ item.open?"▼":"▶"}}</span>
      </div>

      <div v-show="item.open">
        {{ item.content }}
      </div>

    </div>


  </div>
</template>


<style>


  .container{
    width: 700px;
    display: flex;
    flex-direction: column;
    row-gap: 1rem;
    border: 1px solid rgb(203, 198, 198);
    border-radius: 10px;
    justify-content: center;
    align-items: center;
    padding: 30px 0;
  }

  .acc{
    background-color: rgb(36, 86, 252);
    color: white;
    padding: 10px 100px;
    width: 400px;
    text-wrap: wrap;
    text-align: center;
    border-radius: 5px;
    font-family:'Courier New', Courier, monospace;
    font-size: 20px;
  }
  .header{
    font-size: 25px;
    font-weight: bold;
  }

</style>
