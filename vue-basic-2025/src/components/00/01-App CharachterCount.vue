<script setup>
import { ref, computed } from 'vue';

const message = ref('');

const length = computed(() => message.value.length);
const isTooLong = computed(() => length.value > 10);

</script>

<template>
  <div class="box">
    <h2>Character Counter</h2>
    <input v-model="message" placeholder="Type something..." />

    <p :class="{ warning: isTooLong }">
      Length: {{ length }} characters
    </p>
    <p v-if="isTooLong" class="error">
      ⚠️ Too long! Please keep under 10 characters.
    </p>
  </div>
</template>

<style scoped>
.box {
  padding: 20px;
  max-width: 400px;
  margin: auto;
  font-family: Arial, sans-serif;
  border: 1px solid #ccc;
  border-radius: 10px;
  margin-top: 40px;
}

input {
  width: 100%;
  padding: 10px;
  font-size: 16px;
}

.warning {
  color: green;
}

.error {
  color: red;
  font-weight: bold;
}
</style>
