<script setup>
const submitHandler = e => {
  e.preventDefault()

  alert('Valid data')
}
</script>

<template>
  <form class="form" @:submit="submitHandler">
    <input class="input" type="text" placeholder="Enter your first name" />
    <input class="input" type="text" placeholder="Enter your last name" />
    <input class="input" type="password" placeholder="Enter password" />
    <button class="btn incrBtn" type="submit">Log In</button>
  </form>
</template>

<style>
.form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  row-gap: 1rem;
}

.input {
  border-radius: 4px;
  border: 1.5px solid gray;
  outline: none;
  padding: 4px 4px;
}
</style>
