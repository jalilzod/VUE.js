<script setup>
const myChannel = 'www.youtube.com/@webbarnomasozosonfaxmo'

const imageInfo = {
  src: `https://img.freepik.com/free-photo/abstract-autumn-beauty-multi-colored-leaf-vein-pattern-generated-by-ai_188544-9871.jpg`,
  alt: `Just a foto`,
  width: 300,
  height: 200,
}
</script>

<template>
  <a :href="myChannel">My youTube channel</a>
  <!-- <img v-bind:="imageInfo" /> -->
  <img :="imageInfo" />
</template>
