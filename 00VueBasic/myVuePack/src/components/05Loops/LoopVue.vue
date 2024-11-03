
<script setup>
import { ref } from 'vue'

let quotes = ref([
  {
    quote:`"Discipline is the bridge between goals and accomplishment."`,
    person:` — Jim Rohn`
  },
  {
    quote:`"The only discipline that lasts is self-discipline."`,
    person:` — Bum Phillips`
  },
  {
    quote:`"Self-discipline is the magic power that makes you virtually unstoppable." `,
    person:` — Dan Kennedy`
  },
  {
    quote:`"You have power over your mind—not outside events. Realize this, and you will find strength."  `,
    person:` — Marcus Aurelius`
  }

]);

</script>


<template>

  <div v-for="(quote,index) of quotes" :key="index">
    <p class="parag-text">{{ quote.quote }}</p>
      <h1 class="head-text">{{ quote.person }}</h1>
  </div>
  <button class="btn incrBtn" @click="show = !show">More</button>
</template>


<style>

</style>
