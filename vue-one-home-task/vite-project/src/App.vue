<script setup>
import { ref, onMounted } from 'vue';

const formattedDate = ref('');

onMounted(() => {
  formattedDate.value = new Date().toLocaleString('ru-RU', {
    weekday: 'long',
    year: 'numeric',
    month: 'long',
    day: 'numeric',
  });
});
</script>

<template>
  <div>
    <h1>Сегодня:</h1>
    <p class="date">{{ formattedDate  }}</p>
  </div>
</template>

<style scoped>
.date {
  font-size: 30px;
}
</style>
