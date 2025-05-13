<template>
  <div class="start-screen">
    <h1>Запомни слово</h1>
    <button @click="$emit('start')">Начать игру</button>
  </div>
</template>

<script setup></script>

<style scoped>
.start-screen {
  text-align: center;
  margin-top: 100px;
}
button {
  padding: 10px 20px;
  font-size: 16px;
}
</style>